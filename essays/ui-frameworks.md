---
layout: essay
type: essay
title: 'Do UI Frameworks Work?'
# All dates must be YYYY-MM-DD format!
date: 2023-02-23
published: true
labels:
  - Software Engineering
  - Bootstrap
  - Tailwind
  - Material UI
---

### Here’s the tl;dr

I like using UI frameworks because they make creating specific components easier, but you don’t have the same customizability as using plain CSS, and sometimes a CSS solution is easier to implement.

### What is a UI framework?

A UI framework is a framework (_duh_) for making user interfaces (_duh_ x2). For web development, think of them as a layer on top of plain HTML, JS, and CSS. They package them together in reusable components that make it easier to build web applications. They can be as constrict as whole button components, or as free as a div that comes with `display: flex;`. They can help in designing layouts, making responsive websites, etc.

### So, why use a UI framework?

I understand the appeal of using a UI framework like Bootstrap. Many websites have similar layouts with common components, like a navbar, footer, maybe a hero image, etc. Bootstrap is an easy way to implement all these things. All the bootstrap components are “high-level”, so they don’t go into too much detail on how each component works. From this, you get easy-to-use, standardized components that can be placed into any project. The drawback being that a bootstrap website looks like, well, a bootstrap website.

The other advantage that Bootstrap provides is all its utility classes. Making a div a flexbox, for example, is very simple to do with Bootstrap (just add `d-flex` to the div’s class list). However, if you want to start doing things custom, you’ll find yourself writing something like:

```html
<div class="d-flex flex-column align-items-center justify-content-center gap-2">
  😵
</div>
```

before you realize you just wrote as much as I would doing it in normal css.

That’s the same realization I had while learning and working with Bootstrap. I appreciate things like a navbar class for navs or a container on a div to make its max-width responsive, but many of the utility classes are mostly a waste of time. When you just need a quick fix on a single element, like making the text bold, is it really easier to add `class="fw-bold"` instead of `style="font-weight: bold;"` or wrapping it in <b></b> tags?

### Other UI frameworks:

#### Tailwind

I tried another popular CSS framework that makes everything a utility class, called Tailwind. A lot of people like it because it removes one of the hardest things in coding: naming things. Say goodbye to class names like middle-section-container... say hello to extremely ugly HTML because classnames end up being entire lines long.

An example from the Tailwind homepage:

```html
<div
  class="grid gap-4 col-start-1 col-end-3 row-start-1 sm:mb-6 sm:grid-cols-4 lg:gap-6 lg:col-start-2 lg:row-end-6 lg:row-span-6 lg:mb-0"
>
  ...
</div>
```

If you really hate writing CSS, then I could see it making things easier, but to me it’s not worth the hassle.

#### Material UI

Another framework called Material UI is similar to bootstrap in that it defines premade components, the difference being it is a React component library, not a CSS? library. Since Material UI uses Google’s Material Design, everything looks very professional and like it’s a Google product, so if that’s the style you are looking for, Material UI does the job very well. It’s not as open as Bootstrap or Tailwind since it forces you to use the Material Design system, but if you didn’t want to, you wouldn’t be using MUI.
