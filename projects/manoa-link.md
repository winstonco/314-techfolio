---
layout: project
type: project
image: img/manoa-link/logo-green-bg.png
title: 'Manoa Link'
date: 2023-05-02
published: true
labels:
  - Meteor
  - React
  - Sass
  - Testcafe
summary: 'An app to connect employers directly with students looking for internships and other opportunities.'
---

![landing page](/img/manoa-link/landing.png)

### What is Manoa Link?

For my Software Engineering I final project, me and three other students: Jared Lo, Honggun Jeon, and Prayag Das, created an app to solve the problem that all computer science students face: finding jobs. We all know that it is important to get an internship. You learn a lot more in a professional environment than in a classroom, and you can network and make connections for opportunities after you graduate.

However, the hardest part is getting your name known. It might seem impossible to get your name out there, and with other platforms, it is hard to tell if companies are really looking, which is why we created Manoa Link.

_From our [project page](https://uhmanoalink.github.io/):_

Manoa Link is an innovative web platform designed to facilitate easy meetups between students, job seekers, and companies. It serves as a one-stop solution for students looking to connect with potential employers, explore job opportunities, and attend industry events. With dedicated interfaces for students and companies, ManoaLink streamlines the process of building relationships, fostering growth, and creating meaningful connections.

### [<img style="height: 2em;" alt="Meteor.js logo" src="../img/manoa-link/meteor-logo-full.png" />](https://www.meteor.com/)

#### This section is all about my thoughts about the Meteor framework. If this sounds interesting, keep reading! If not, you can [skip this section](#development).

In class, we learned about the Meteor framework, which lets developers easily build full-stack applications. Although now it's a bit old, Meteor's community is robust, so there are Atmosphere packages that solve most problems.

This was my first time using Meteor, and will probably be my last. I see how it can be appealing to some developers, but to me, in the process of simplifying it actually overcomplicated.

#### 👍 What I liked

I liked how it simplified things like account creation, user authentication (which we never used), and (somewhat) database manipulation. Like I said, the package library is also really large, not even including NPM packages. The monorepo style also makes it easy to switch between working on the frontend and backend.

#### 👎 What I disliked

The main things I disliked were related to the database. Okay, I know I said database manipulation is something I liked about Meteor. What I was talking about is the Tracker, which lets pages and components stay up-to-date, with automatic updates as the database changes.

In the month of working on the project, I never fully understood how Minimongo worked or how to use Meteor Methods vs pub/sub. I mean, conceptually, I get all of them. Minimongo caches a subset of the full database, giving fast reads and updates as if the database was in memory. Meteor Methods let you call server-side functions from the client. And pub/sub is, well, pub/sub. As someone more familiar with using a REST API to query the database, and a more clear separation between server and client, it was hard to wrap my head around Meteor's system.

For example, in many instances, I would've preferred to use a Meteor Method to find a document over subscribing to a publication since it is less resource intensive and instant updates were not necessary. But I still needed to subscribe anyway? Really? There's a good chance that I was using Meteor Methods incorrectly, but those are confusing enough already!

According to the docs, they, as well as any MongoDB method, are synchronous (unless you give it a callback function), but that wasn't always the case. One of our methods called `findOne` (should be synchronous on the server) and returned the document found.

It might look something like:

```js
Meteor.methods({
  ...
  findOne(collectionName, selector) {
    check(collectionName, String);
    check(selector, Match.OneOf(Object, String, Mongo.ObjectID, Mongo.Selector));
    // We used the package 'dburles:mongo-collection-instances' for the get method
    const collection = Mongo.Collection.get(collectionName);
    return collection.findOne(selector);
  },
  ...
});
```

Then we called the method with something like:

```js
// This isn't exactly accurate, but is just an example
const winstonDoc = Meteor.call('findOne', 'students', { name: 'Winston' });
```

When we did something like this, it confused me that we still needed to subscribe to any publications since the server would already have access to all the collections. Also, it would sometimes return `undefined` first, leading me to believe it's not actually synchronous.

#### Okay, enough about Meteor

### Development

In my team, it seemed I was the only one with experience in software development, let alone web development. Naturally, I took on the roles of both project manager and lead developer. Just from how my schedule was, I had a lot more time to work on the project than my team members, so I got very familiar with the project and tried my best to help my team with their issues.

Though it slowed development, I made sure to enforce good practices by setting up CI to run ESLint checks and our tests. I tried to make sure our tests accurately tested each aspect of the project. I set up the GitHub repository so that pull requests required approval from at least one person, and whenever I reviewed someone's changes I made sure they were following good practices, updating documentation, and cleaning up other areas of conflict. I tried to keep the style consistent throughout the project as best I could.

Since the project was already a big undertaking and my teammates were new, I didn't want to overwhelm them with too many new things. First, I introduced them to [<img style="height: 1em;" alt="TypeScript logo" src="../img/manoa-link/typescript-logo-full.png" />](https://www.typescriptlang.org/), but only for our test files, so that a) writing tests is easier and b) maybe they see why TypeScript is so great. I also introduced them to [<img style="height: 1em;" alt="Sass logo" src="../img/manoa-link/sass-logo.png" />](https://sass-lang.com/) to make our CSS modular. I don't think my teammates got any value out of either, but hopefully now they are at least a bit more familiar if they come across them in the future.

#### My contribution

It's hard to pinpoint what I worked on since I generally contributed throughout the entire project.
