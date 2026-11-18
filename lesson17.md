<!-- .slide: id="lesson17" -->

# JavaScript Course - Fall 2026

Lesson 17, Tuesday, 2026-11-24

---

# Peer Review
#### Reviewing others, reviewing yourself, and AI as a second reviewer

---

### Recap: Lesson 16

- Final project: 1–3 people
- Deliverables: JS solution, 5-min presentation, live demo
- Planning: weekly task breakdown for your MVP (nice-to-haves last)

---

### Today's objective

After this lesson you can:

- Give a clear, constructive review comment on someone else's code
- Receive a review and respond: keep, change, or ask
- Apply the same checks to your own code
- Use AI as a second reviewer, without letting it think for you

---

### Agenda

- Warm-up: review code cold (10 min)
- Part 1: Peer review (35 min)
- Exercise 1: review a classmate's project (25 min)
- Break
- Part 2: Self-review (15 min)
- Part 3: AI as a second reviewer (25 min)
- Wrap-up (10 min)

---

> This is a new lesson format we are experimenting with this semester, feedback welcome!

---

<!-- .slide: id="warm-up" -->

# Warm-up

No theory yet. Just read and react.

---

Look at this code. What would you tell the author?

Take 1 minute alone, then 1 minute with your neighbour.

```js
let n = 3;
let p = 8;
console.log(n * p);
```

---

Same question. Does the output look right?

```js
let numFriends = 2;
let ticketPrice = 2;
let totalPrice = numFriends ** ticketPrice;
console.log(totalPrice); // output is 4
```

---

Reveal: the bug is hidden by a coincidence

- `2 ** 2` and `2 * 2` are both `4`
- The output looks correct, the code is wrong
- Try `numFriends = 3` and you will see it
- Lesson: "it runs" is not the same as "it is right"

---

<!-- .slide: id="peer-review" -->

# Part 1: Peer Review

---

### What is peer review?

One or more people examine the work of someone else, usually before the code is considered ready.

You just did it: you read code you did not write and said something about it.

---

### Why peer review?

- Catches bugs early, when they are cheap to fix
- Improves clarity and maintainability
- Spreads knowledge: you learn from other people's code
- Builds team communication
- It is _not_ just about finding mistakes

---

### What do reviewers look at?

In this order:

1. Correctness: does it do what it should?
2. Edge cases: what if the input is empty, zero, or missing?
3. Design: is the structure sensible?
4. Readability: names, comments, simplicity
5. Style nitpicks (spacing, quotes) come last

---

Which of the 5 levels is this? Discuss in pairs.

```js
let items = [10, 20, 30];
let total = 0;
for (let i = 0; i <= items.length; i++) {
  total = total + items[i];
}
console.log(total); // NaN
```

---

Level 1, correctness: an off-by-one bug

- `i <= items.length` goes one step too far
- `items[3]` is `undefined`, and `30 + undefined` is `NaN`
- Fix: `i < items.length`

---

Which level is this?

```js
let status = "active";
if (status = "inactive") {
  console.log("User is inactive");
}
```

---

Level 1, correctness: `=` assigns, `===` compares

- The condition assigns `"inactive"`, a non-empty string
- A non-empty string is truthy, so the `if` always runs
- Fix: `status === "inactive"`

---

Which level is this?

```js
function average(numbers) {
  let sum = 0;
  for (let i = 0; i < numbers.length; i++) {
    sum = sum + numbers[i];
  }
  return sum / numbers.length;
}
```

---

Level 2, edge cases: what if `numbers` is empty?

- `0 / 0` is `NaN`
- Do not just "fix" it: ask the author what the expected result is
- A question invites discussion, an order does not

---

Which level is this?

```js
function f(x) {
  return x * 0.9;
}
```

---

Level 4, readability

- Unclear name: what does `f` do?
- Magic number: what is `0.9`?
- Suggestion: `applyDiscount(price)` with a named rate

```js
let DISCOUNT_RATE = 0.9;

function applyDiscount(price) {
  return price * DISCOUNT_RATE;
}
```

---

Which level is this?

```js
function isUserActive(user) {
  if (user.isDeleted === true) {
    return false;
  } else {
    return true;
  }
}
```

---

Levels 3 and 4: it works, but it can be simpler

```js
function isUserActive(user) {
  return user.isDeleted !== true;
}
```

Also a good question for the author: can `isDeleted` be missing?

---

<!-- .slide: id="good-comments" -->

### How to write a good comment

- Talk about the code, not the person
- Be specific: point to the line, explain the effect
- Ask questions that invite discussion
- Suggest, don't just criticize

---

Bad comment vs good comment

| Bad | Better |
|---|---|
| "You always write unclear code." | "I did not understand what `f` does. Would `applyDiscount` be clearer?" |
| "This is wrong." | "If `numbers` is empty this returns `NaN`. What should happen then?" |
| "Why didn't you use `===`?" | "`=` assigns here, so the `if` always runs. Did you mean `===`?" |

---

Your turn: rewrite this comment

> "This loop is a mess, fix it."

Take 2 minutes. Then compare with your neighbour.

---

### Receiving feedback

- Let go of ownership: the code is the team's, not yours
- Do not defend, first understand the question
- For every comment, answer with one of three:
  - **Keep**: "I'll leave it, because..."
  - **Change**: "Good catch, fixed."
  - **Ask**: "Can you explain what you mean?"

---

<!-- .slide: id="exercise-1" -->

### Exercise 1: review a real project

In pairs, swap code from your final project (or an earlier task).

1. Read your partner's code, no AI yet
2. Write 3 review comments: use the 5 levels and the good-comment rules
3. Swap back: the author answers each comment with keep, change, or ask
4. Talk about one comment that surprised you

---

# Break Time!

---

<!-- .slide: id="self-review" -->

# Part 2: Self-Review

---

### Self-review is peer review, aimed at yourself

You now know what a reviewer looks for.
Before you hand over your code, be your own first reviewer.

It saves time for others, and it catches the embarrassing mistakes.

---

Use the same 5 levels on your own code:

1. Correctness: does it actually do what I think it does?
2. Edge cases: empty, zero, missing input?
3. Design: is the structure sensible?
4. Readability: would a teammate understand this?
5. Style: last

And one extra question: would I understand this in 6 months?

---

Why is self-review harder?

- You see what you meant, not what you wrote
- You know the context, the reader does not

---

Habits that help

- Take a break before reviewing
- Read your git diff before you share it
- Rubber ducking: explain the code out loud, line by line
- Test with the boring inputs: `0`, `[]`, `undefined`

---

Try it: self-review this code in 2 minutes

```js
function findMax(numbers) {
  let max = 0;
  for (let i = 0; i < numbers.length; i++) {
    if (numbers[i] > max) {
      max = numbers[i];
    }
  }
  return max;
}

console.log(findMax([-5, -2, -9])); // 0 ?
```

---

Reveal

- Level 1: `max` starts at `0`, so all-negative arrays return `0`
- Level 2: an empty array returns `0`, is that intended?
- Fix: start with `let max = numbers[0];` and decide what happens for `[]`

---

<!-- .slide: id="ai-review" -->

# Part 3: AI as a Second Reviewer

---

### Human first, then AI

- Do your own review first (peer or self)
- Then ask AI, and compare
- If AI goes first, you stop thinking and start agreeing

---

### What AI is good at

- Spotting common bugs and code smells
- Suggesting simpler versions
- Offering alternatives you did not think of
- Helping with the tone of a comment

---

### What AI is not good at

- Knowing your intent and your project's context
- Knowing what your teacher or team expects
- Being right: it can sound confident and be wrong

You are the reviewer. AI is a second opinion.

---

### Prompt suggestions

- "If I submitted this to a code review, what would be the top 3 concerns?"
- "What edge cases does this function not handle?"
- "How would you improve this function for clarity?"
- "Is this comment polite and specific? Suggest a better wording."

---

### Exercise 2: compare yourself with AI

1. Take the code you reviewed in Exercise 1 (or your own code)
2. Write down your own findings first
3. Ask AI for a review
4. Sort every AI point: **keep**, **change**, or **ask**
5. Answer: what did AI catch that you missed? What did you catch that AI missed?

---

### Layers of review

No single check catches everything.

- Self-review
- Running and testing the code
- Peer review
- AI as a second opinion

Each layer catches different problems. They add up, they do not replace each other.

---

<!-- .slide: id="wrap-up" -->

### Wrap-up: show what you learned

On a piece of paper or in the chat:

1. Write 2 review comments about a snippet we saw today
2. Swap with a partner: is each comment specific, about the code, and respectful?
3. Write one sentence: "In my final project I will review ___ before I share it."

---

### Reflect as a group

- Which review level did you miss most often?
- Did AI surprise you? Where was it wrong?
- Was it harder to review yourself or someone else?

---

Additional Resources:

<!-- .slide: style="font-size:80%" -->

* [Why you need a self review of your code](https://medium.com/bitdatatechie/why-you-need-a-self-review-of-your-code-4ea057f428fa)
* [How to review code effectively: A GitHub staff engineer's philosophy](https://github.blog/developer-skills/github/how-to-review-code-effectively-a-github-staff-engineers-philosophy/)
* [How to do a code review](https://google.github.io/eng-practices/review/reviewer/)
* [Code Review good practices: guide for beginners](https://medium.com/transparent-data-eng/good-practices-of-code-review-guide-for-beginners-8c084cd70be3)
* [Review your own pull requests](https://patrickdinh.medium.com/review-your-own-pull-requests-5634cad10b7a)
* [Empathy and code reviews](https://medium.com/@RoxSWEngineering/empathy-and-code-reviews-fde4e394184d)
