---
layout: essay
type: essay
title: 'What Makes a Good Question?'
# All dates must be YYYY-MM-DD format!
date: 2023-01-25
published: true
labels:
  - Software Engineering
  - Netiquette
  - Stack Overflow
---

### Smart Questions

Asking questions is one of the hallmark qualities of a software engineer. Asking smart ones is a quality of good ones. At least, that’s what I took away after reading [_How to Ask Questions the Smart Way_](http://www.catb.org/esr/faqs/smart-questions.html). It was a good read; a little dry, but that was expected given the subject matter. A lot of it was common sense in hindsight, but it’s helpful to have it explained fully. I mean, isn’t it obvious that asking the right questions will give you the right answers?

_Obviously_ writing a good subject header (or Stack Overflow question) is necessary.

_Obviously_ showing relevant details about a problem and how you tried to solve it is necessary.

_Obviously_ just posting homework questions is a no-no (though personally, I don’t think these people are really expecting an answer).

Some of the points that I think were most important especially for asking good questions on Stack Overflow are 1) State facts. Don’t assume things about your problem. 2) Format your post, and find the section of code (or whatever) that is the root of your problem, if possible. 3) “Describe the goal, not the step.” You might think you know what a solution looks like, but yours might be makeshift or ill-informed. Instead, let the community guide you toward what the solution should look like.

### A bad question

When I looked on Stack Overflow, I didn’t have to search hard to find [a bad question](https://stackoverflow.com/questions/25472744/can-anyone-solve-this-error-in-jdbctemlate). You can tell it is a bad question just from the title itself. All the poster did is give an error log and write

> “Can anyone solve this error in **Spring** using `JdbcTemplate`. Here is the Error-”.

The replies to the post ask for more details, but the poster never followed up or updated their question. The only answer received explained possible issues and a command they could run to find the source of the problem. However, I’m not even sure if this was even helpful because the poster never marked it as accepted.

### A good question

By contrast, here’s what I think is [a pretty good post](https://stackoverflow.com/questions/67652612/chunkloaderror-loading-chunk-node-modules-next-dist-client-dev-noop-js-failed/67659159#67659159). The poster states they’ve been following the tutorial on the Next.js website, which makes the error very reproducible. To me, the title of the post says enough. It’s clearly a Next.js error from the `next_dist` part and the post’s tags. They included the error message and images of the error message shown on client-side. The accepted answer is very helpful; they explain how they went through GitHub issues and blog posts trying to find an explanation, but the error is a caching error, probably caused by strange Next.js behavior. Looking at others’ replies, the error is common and replicable in many ways. A post such as this bringing a common problem to light will hopefully lead to an issue being posted and improvements being made to the framework/app/program/etc.

Here’s another example of [a good post](https://stackoverflow.com/questions/37233735/interfaces-vs-types-in-typescript). Now, looking at some of the guidelines, why is this post good? Well, to start off, the post is extremely succinct and straight to the point. They want to know the difference between Interfaces and Types in TypeScript. The poster shares two seemingly functionally equivalent statements.

```ts
interface X {
  a: number;
  b: string;
}
type X = {
  a: number;
  b: string;
};
```

You might be wondering how this shows any work done on the poster’s part. Short answer: it doesn’t. But I don’t think it has to. The point of the post is obviously for clarifying purposes, and by looking at the answers, the documentation at the time of posting was not very clear on the difference. The post also evolved to be a forum of its own, so answers can get updated as the TypeScript docs are updated.
