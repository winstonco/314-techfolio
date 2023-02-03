---
layout: essay
type: essay
title: 'Junior Self-Developer'
# All dates must be YYYY-MM-DD format!
date: 2023-02-02
published: true
labels:
  - Software Engineering
---

### I like coding.

My interest in software engineering is mostly from finding it fun and rewarding to envision something and make it. I like working on a project and being able to see tweaks as I make them. I also like being able to easily see myself improving, at least for now.

---

### A short history lesson :books:

My earliest memory of actual exposure to computers was in lower school. We had a computer class where we learned to type with Mavis Beacon Teaches Typing and learned to code with [Scratch](https://scratch.mit.edu). That class sparked my interest in coding, especially in making games, and from then on I wanted to be a game developer. I spent a lot of time on the library computers tinkering in Scratch, never making anything substantial, but making a lot nonetheless.

In high school, I took AP Computer Science Principles, which for the most part used [Processing Java](https://processing.org/). With their easy-to-use canvas and simple library, I had a ton of fun making visual projects and even used it after the class to make a project for Chinese.

<div style='display: grid; grid-template-columns: repeat(3, 1fr); gap: 1rem'>
  <div>
    <img class='img-fluid' src='../img/se-interests/processing-smash.png'>
    Final Project:<br>
    A multiplayer "Smash Bros. clone", but without fighting. Clients connected to a server host running on the same network.
  </div>
  <div>
    <img class='img-fluid' src='../img/se-interests/processing-ping-pong.png'>
    Semester Project:<br>
    A 3D ping pong game, where you control one paddle and a computer controls the other (it just follows the ball perfectly).
  </div>
  <div>
    <img class='img-fluid' src='../img/se-interests/processing-chinese.png'>
    Chinese Project:<br>
    An interactive game where you explore the map to complete quests, in Chinese.
  </div>
</div>

### :computer: Web development or :video_game: game development?

Last October, I delved a bit in learning web development, just 'cause I thought it'd be fun. From lower school until then, I was pretty set on being a game developer, but web dev. turned out to be a lot of fun, so I had to decide what to pursue. I was kind of torn, so I asked around for advice at events with both fullstack engineers and game developers. The general consensus was that since web dev. has higher demand (plus, games need websites too), if the decision is split 50/50, go forth with web development.

I took their advice and chose to be fully dedicated to learning web dev. and haven't had any regrets (for now). One guy I spoke to suggested I just make a web game, the best of both worlds, and I must just love making games, because the project I've had the most fun making is [a game](/314-techfolio/projects/sham-ill.html).

I'm interested in both, so I guess there isn't really a right answer :shrug:.

---

### What I'm looking forward to learning:

In my head, I have a clear plan on what new technologies and tools I want to learn.

Full list in order of interest (most -> least):

- More TypeScript
- More React.js
- MongoDB
- [Next.js](https://nextjs.org/) & [Next 13](https://beta.nextjs.org/)
- [Cypress](https://www.cypress.io/)
- Docker
- [Vitest](https://www.cypress.io/)
- [Svelte](https://svelte.dev/) / [Astro](https://astro.build/) / [Solid](https://www.solidjs.com/)
- [PocketBase](https://pocketbase.io/)
- [Nginx](https://www.nginx.com/)

#### Frontend

I want to learn the advantages of using a meta framework like [Next.js](https://nextjs.org/), and after that, what's new in [Next 13](https://beta.nextjs.org/). I also want to learn other popular frameworks like [Svelte](https://svelte.dev/), [Astro](https://astro.build/), and [Solid](https://www.solidjs.com/), which I've read and heard good things about. However, I know I'm getting a bit ahead of myself, and I'm getting more familiar with React before moving on.

#### Backend

Admittedly, I have a lot to learn about backend technologies. The most I've done is set up basic API routes to fetch data from a database. I'm looking at learning [Nginx](https://www.nginx.com/) or maybe a BaaS provider like [PocketBase](https://pocketbase.io/). In terms of database stuff, which I'll include in 'backend', I've only done a small bit of MongoDB (or any database work), so very I'm excited to learn more about it.

#### Other

Of course, I'm still learning the ins-and-outs of TypeScript. I heard most developers mainly just use it to add typing and IDE tooling to what otherwise would be normal JavaScript _(source: just trust me)_, but regardless I think it will always be beneficial to be more comfortable using the language.

One thing I'm embarrassed to say is that I don't write tests for my projects, but I'm going to change! I'm planning on learning [Cypress](https://www.cypress.io/) to write E2E tests and [Vitest](https://www.cypress.io/) to write any unit tests (since the project was built with Vite).

I recently tried using Docker to containerize a project, but I barely scratched the surface. All I did was write a basic Dockerfile. Since the project has separate frontend and backend that should maybe deploy together, I'm planning to research how to use Docker Compose to join two containers and whether this approach even makes sense in the first place.
