<!-- .slide: id="lesson17" -->

# JavaScript Course - Fall 2026

Lesson 17, Thursday, 19.11.2026

---

> this is a new lesson format we are experimenting with this semester, feedback welcome!

---

# Peer Review

One or more people examine the work of someone else. Usually happens in teams before considering the code to be ready.

---

### Why peer review?

- Helps catch bugs early on
- Improves code quality, reliability, and maintainability
- Enhances learning through feedback
- Promotes team collaboration and communication

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

### AI Tools

You can use AI tools to help you do the review, but you need to _ask the right questions_, and _think critically about the output._


---

### Demo with ChatGPT

---

Now try it with some of your code from previous tasks

* What did it say? Does it make sense?
* Do you know if its better? why?
* Can you change adapt your code accordingly?

---

Additional Resources:

* [Why you need a self review of your code](https://medium.com/bitdatatechie/why-you-need-a-self-review-of-your-code-4ea057f428fa)
* [How to review code effectively: A GitHub staff engineer’s philosophy](https://github.blog/developer-skills/github/how-to-review-code-effectively-a-github-staff-engineers-philosophy/)
* [How to do a code review](https://google.github.io/eng-practices/review/reviewer/)
* [Code Review good practices: guide for beginners](https://medium.com/transparent-data-eng/good-practices-of-code-review-guide-for-beginners-8c084cd70be3)
* [Review your own pull requests](https://patrickdinh.medium.com/review-your-own-pull-requests-5634cad10b7a)
* [Empathy and code reviews](https://medium.com/@RoxSWEngineering/empathy-and-code-reviews-fde4e394184d)

