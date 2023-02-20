---
layout: essay
type: essay
title: 'Why Use ESLint'
# All dates must be YYYY-MM-DD format!
date: 2023-02-09
published: true
labels:
  - Software Engineering
  - ESLint
---

### But why should I use a linter?

_It makes coding soo annoying~_ 😩

Even if it’s "annoying", the importance of following coding standards makes it well worth doing. It makes your code more readable, which helps you when you go back through it, and other people who look at your code and try to understand what it does. It also helps in finding bugs, because writing cleaner code leads to less bugs (like unreachable code after a return).

#### Style examples

Every language has its own “shape” and a set of standards that match it. For example, in C#, it is common to have curly braces on a new line for functions, classes, interfaces, etc.

```c#
public static void main(string[] args)
{
  // Some code
}
```

while in JavaScript, curly braces start on the same line.

```js
const main = () => {
  // Some code
} // notice anything wrong?
```

or

```js
function main() {
  // Some code
}
```

One thing that is required in C# but optional in JavaScript is putting a semicolon at the end of lines. Even though it is optional in JavaScript, it again helps with readability by marking the end of lines.

And actually, in the example above, since the first function declaration is just assigning an anonymous function to the variable name `main`, it actually requires a semicolon at the end of the line.

```js
const main = () => {};
```

Just like:

```js
const PI = 3.14;
```

### Using ESLint

Personally, I don't have much trouble following ESLint's rules. I like to think I already write pretty clean code, but I think it's because most JS standards are pretty intuitive, like putting spaces around your arrows, always putting semicolons, and making sure variables are used. I _do_ forget to put semicolons at the end of arrow functions, though.

One thing that confused me is that the per-line character limit clashes with one-line arrow functions.

Here’s an example of what I mean:

```js
const aLongFunction = (data) =>
  data.manipulateToSomething.manipulateAgain.hereIsAReallyLongFunction
    .theLastLongFunctionName;
```

Okay, I get why it’s a problem to have absurdly long lines. After all, it's really hard to read what's going on here, so I tried to split it using braces, like so:

```js
const aLongFunction = (data) => {
  return data.manipulateToSomething.manipulateAgain.hereIsAReallyLongFunction
    .theLastLongFunctionName;
};
```

However, even though this now fits the character limit, ESLint requires functions that have just a return statement to be on one line (no curly braces), which just goes back and forth failing each other.

The fix is to split it more so there isn’t just a return statement:

```js
const aLongFunction = (data) => {
  const manipulatedData = data.manipulateToSomething.manipulateAgain;
  return manipulatedData.hereIsAReallyLongFunction.theLastLongFunctionName;
};
```

By breaking the logic across more steps, it's easier to see each step of how the data is being used in this function.

So far, this is the only thing I was a little annoyed about, but if that’s how they want it, there’s no point being annoyed. I mean, I’ll just write it like that next time.

Which leads me into the next point.

### It's not a big deal to follow convention

Some people might ask “who cares?” or “why?”. To me, this isn’t even the question people should be asking. What they should really be asking is “what?” as in, “what else should I be doing?” because it’s not like any of the rules are that hard to follow, it’s just a convention.

It would be like if someone never dotted their i’s when writing. Even if you can still read the word without the dots there, it just makes it hard to read and it’s such an easy fix (just put the damn dot after you write the line). Or a more egregious example is putting every sentence of a paragraph on a new line. Unless they’re a poet, it just makes the piece hard to read.

The same can be said for coding standards.

#### An aside:

One thing that linters (sadly) cannot help with is one of the hardest things in programming: naming things.

### A note on Prettier

<img class="img-fluid" src="../img/coding-standards/prettier.png">

One tool I use all the time is called Prettier, self-described as “an opinionated code formatter”. ‘Formatter’ meaning it fixes your code style for you, and ‘opinionated’ meaning there is a default style guide that “should” be used. Of course, you can configure it to follow your own guidelines, but the point of using Prettier is to eliminate debate on style.

There is some overlap, but Prettier is different from ESLint because ESLint (and other linters) helps to write good quality code, not just well formatted. Prettier won’t catch unused variables, for example.
