---
layout: essay
type: essay
title: 'Design Patterns'
# All dates must be YYYY-MM-DD format!
date: 2023-04-27
published: true
labels:
  - Software Design
  - Design Patterns
---

### What are design patterns?

Design patterns are used in software design to solve common problems. They are commonly found chunks of code that make it easy to understand a problem and its solution. They also make it easier for other programmers to understand your work and what you’re trying to achieve. While I know a number of them, I don’t think too much about using them while I code (aside from the basic ones). Still, I happen to use design patterns whether I’m thinking about it or not, so here are some examples (using the definitions at [Patterns.dev](https://www.patterns.dev/)):

### Singleton

*“Singletons are classes which can be instantiated once, and can be accessed globally. This single instance can be shared throughout our application, which makes Singletons great for managing global state in an application.”*

In my personal “[Illustraitor](https://winstonco.org/314-techfolio/projects/illustraitor)" project, I used a singleton for the `CanvasDrawerInstance` class, since the HTML canvas element can only have one context, only one class that draws to it could exist.

Another example is in “Manoa Link”, a class project made by a small team of 4. Each collection was its own singleton, with properties like the name of the collection, the collection itself, publication names, etc.

> One thing to note is that in JavaScript, the singleton pattern being a “global instance of a class”  is just a carryover from OO languages like Java. In JS, you would probably just use an object literal.

### Higher Order Components

*“A Higher Order Component (HOC) is a component that receives another component.”*

In Manoa Link, I made a component called ProtectedRender, a HOC that took in a child element and only rendered it under the right conditions.

```jsx
const ProtectedRender = ({ allowedRoles, children }) => {
  if (allowedRoles === undefined) {
    return (Meteor.user()) ? children : null;
  }
  return (allowedRoles.some(
    (role) => Roles.userIsInRole(Meteor.userId(), role),
  ))
    ? children
    : null;
};
```

### Factory

*“A function is a factory function when it returns a new object without the use of the new keyword!”*

In a recent addition to Manoa Link, I added functionality for file uploading. The package I used was a Meteor Atmosphere package called [ostrio:files](https://packosphere.com/ostrio/files). While following their templates for saving files using GridFS, MongoDB’s specification for large file storage, I noticed that a few of the functions they defined were factory functions to create handlers! One example is `createInterceptDownload`, which I’m showing the first few lines of below.

```jsx
export const createInterceptDownload = bucket => (
  function interceptDownload(http, file, versionName) {
    const { gridFsFileId } = file.versions[versionName].meta || {};
    if (gridFsFileId) {
      ...
```

So basically, design patterns are everywhere. In fact, there are even more that I use all the time, which I’m not going into, like Modules, Hooks, Static Imports and Preload/Prefetch!

### Go to Patterns.dev #not-sponsored

Okay, it’s linked above, but here it is again: https://www.patterns.dev/. I highly recommend learning more about design patterns by looking through the sections on their website or reading their book. Design patterns are great to learn and using them effectively is something that programmers should strive to do.
