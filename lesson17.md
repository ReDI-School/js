<!-- .slide: id="lesson17" -->

# JavaScript Course - Fall 2026

Lesson 17, Tuesday, 2026-11-24

---

# Peer Review & AI Assisted Review

Give and receive feedback, with and without help from AI tools.

---

### Recap: Lesson 16

- Final project: individual or team of 2-3 people
- Requirements: a JavaScript solution, a 5-minute presentation and a live demo
- Define an MVP and break it into tasks, week by week
- Nice-to-have features come only after the essentials work

---

### Today's objective

- Understand what peer review is and why it matters
- Use AI to review your own work
- Review someone else's work with empathy
- Write clear, constructive feedback

---

> this is a new lesson format we are experimenting with this semester, feedback welcome!

---

### Agenda

- Part 1: Peer review and self-review
- Part 2: Reviewing your own work with AI
- Break
- Part 3: Reviewing someone else's work
- Wrap-up

---

<!-- .slide: id="peer-review" -->

# Part 1: Peer Review

One or more people examine the work of someone else. Usually happens in teams before considering the code to be ready.

---

### Why peer review?

- Helps catch bugs early on
- Improves code quality, reliability, and maintainability
- Enhances learning through feedback
- Promotes team collaboration and communication
- It is _not_ just about finding mistakes

---

### How to do it right

- Review code for clarity, not just bugs
- Suggest improvements, don’t just criticize
- Ask questions if unclear about logic

---

Give your feedback on this code:

```js
let n = 3;
let p = 8;
console.log(n * p);
```

Variable names could be better

<!-- .element: class="fragment" -->

---

Give your feedback on this code:

```js
let numFriends = 2;
let ticketPrice = 2;
let totalPrice = numFriends ** ticketPrice;
console.log(totalPrice); // output is 4
```

There is a bug, it should be `*`, not `**`

<!-- .element: class="fragment" -->

---

Give your feedback on this code:

```js
function isUserActive(user) {
  if (user.isDeleted === true) {
    return false;
  } else {
    return true;
  }
}

let userActive = isUserActive(user);
```

It can be simpler: `let userActive = !user.isDeleted`

<!-- .element: class="fragment" -->

---

### Self-Review

before peer review, always look at your code with a critical eye before considering it ready, it saves time for others, and it helps make the code easier to understand.

---

Ask yourself the following questions:

- Would my teammates understand this?
- Would I understand this if I came back to it in 6 months?
- Does this do what it is supposed to do? Does it actually do what i think it does?

---

Some good habits:

- Take a break before reviewing
- Git diffs / Pull requests
- Rubber ducking

---

<!-- .slide: id="self-review-ai" -->

# Part 2: Reviewing Your Own Work with AI

---

### AI Tools

You can use AI tools to help you do the review, but you need to _ask the right questions_, and _think critically about the output._

---

### AI tools: what they do

- Spot code smells / anti-patterns
- Flag accessibility issues
- Suggest refactors and alternatives

---

### Using AI productively

- Good prompts
- Right questions
- Critical thinking about the output

---

### Demo with ChatGPT

---

### Exercise 1

Submit your own work for AI review, for example some of your code from previous tasks

- Critique your code or design with AI
- What did it say? Does it make sense?
- Do you know if it's better? Why?
- Reflect: what did AI catch that you didn't?
- Optional: revise and adapt your code based on feedback

---

# Break Time!

---

<!-- .slide: id="reviewing-others" -->

# Part 3: Reviewing Someone Else's Work

---

### Why it matters

- Builds communication and critical thinking
- Ensures high work quality
- Learn new approaches from others

---

### Best practices

- Work, not the person
- Constructive and specific
- Clarifying questions that invite discussion
- Let go of ownership, learn to receive feedback

---

### AI as a review assistant

- Summarize a snippet / proposal / PR
- Effective prompts for others' work
- Help with tone
- Spot overlooked areas
- Critical thinking about the output

---

### Exercise 2

Review provided snippets with AI support

- Identify areas to focus on, or validate findings
- Review comments: keep, change, ask about
- Discuss how you would phrase feedback to a peer

---

Give your feedback on this code:

```js
function f(x) {
  return x * 0.9;
}
```

Unclear name and a magic number. What is `0.9`? Maybe `applyDiscount(price)` with a named rate

<!-- .element: class="fragment" -->

---

Give your feedback on this code:

```js
let status = "active";
if (status = "inactive") {
  console.log("User is inactive");
}
```

There is a bug: `=` should be `===`. The condition is always truthy

<!-- .element: class="fragment" -->

---

Give your feedback on this code:

```js
function getFirstName(fullName) {
  return fullName.split(" ")[0];
}
```

What if `fullName` is empty or `undefined`? No edge case handling. Ask about the expected input

<!-- .element: class="fragment" -->

---

### Prompt suggestions

- "How would you improve this function for clarity and edge case handling?"
- "What async behavior might cause bugs here?"
- "If I submitted this to a code review, what would be the top 3 concerns?"

---

### Wrap-up

Reflect as a group:

- How do you feel about peer review?
- Surprised by the AI's suggestions?
- Self-review vs. reviewing others?

---

Additional Resources:

<!-- .slide: style="font-size:80%" -->

* [Why you need a self review of your code](https://medium.com/bitdatatechie/why-you-need-a-self-review-of-your-code-4ea057f428fa)
* [How to review code effectively: A GitHub staff engineer's philosophy](https://github.blog/developer-skills/github/how-to-review-code-effectively-a-github-staff-engineers-philosophy/)
* [How to do a code review](https://google.github.io/eng-practices/review/reviewer/)
* [Code Review good practices: guide for beginners](https://medium.com/transparent-data-eng/good-practices-of-code-review-guide-for-beginners-8c084cd70be3)
* [Review your own pull requests](https://patrickdinh.medium.com/review-your-own-pull-requests-5634cad10b7a)
* [Empathy and code reviews](https://medium.com/@RoxSWEngineering/empathy-and-code-reviews-fde4e394184d)
