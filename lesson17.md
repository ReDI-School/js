<!-- .slide: id="lesson17" -->

# JavaScript Course - Fall 2026

Lesson 17, Tuesday, 2026-11-24

---

# Peer Review
#### Reviewing other people's code, your own code, and AI as a second reviewer

---

### Today's objective

After this lesson you can:

- Give a clear, constructive review comment on someone else's code
- Receive a review and respond: keep, change, or ask
- Apply the same checks to your own code
- Use AI as a second reviewer, without letting it think for you

---

### How we work today: the chat

- Everything today happens in the Zoom chat
- When I ask a question, type your answer but **do not press Enter yet**
- When I say "go", everyone sends at once
- This way you think for yourself before you see other answers

---

### Agenda (50 min)

- Warm-up: review code cold (5 min)
- Peer review: what to look for, how to comment (18 min)
- Exercise: review a snippet in the chat (10 min)
- Self-review (5 min)
- AI as a second reviewer (6 min)
- Wrap-up (3 min)

Note: Recap of Lesson 16 is skipped. Show the final project deliverables only if students ask.

---

> This is a new lesson format we are experimenting with this semester, feedback welcome!

---

<!-- .slide: id="warm-up" -->

# Warm-up

No theory yet. Just read and react.

---

Look at this code. What would you tell the author?

Type your feedback in the chat, but don't press Enter yet. (1 min)

Then "go": everyone sends.

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
- "It runs" is not the same as "it is right"

You just did a peer review.

---

<!-- .slide: id="peer-review" -->

# Peer Review

One or more people examine the work of someone else, usually before the code is considered ready.

---

### Why peer review?

- Catches bugs early, when they are cheap to fix
- Improves clarity and maintainability
- Spreads knowledge and builds team communication
- It is _not_ just about finding mistakes

---

### What do reviewers look at?

In this order:

1. Correctness: does it do what it should?
2. Edge cases: what if the input is empty, zero, or missing?
3. Readability: names, simplicity
4. Style nitpicks (spacing, quotes) come last

---

Which level is this? Type 1, 2, 3 or 4 in the chat, then "go".

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

Which level is this? Type 1, 2, 3 or 4 in the chat, then "go".

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

Which level is this? Type 1, 2, 3 or 4 in the chat, then "go".

```js
function f(x) {
  return x * 0.9;
}
```

---

Level 3, readability

- Unclear name: what does `f` do?
- Magic number: what is `0.9`?

```js
let DISCOUNT_RATE = 0.9;

function applyDiscount(price) {
  return price * DISCOUNT_RATE;
}
```

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

---

Your turn: rewrite this comment

> "This loop is a mess, fix it."

Type your better version in the chat (1 min), then "go".

I will pick two and we improve them together.

---

### Receiving feedback

- Let go of ownership: the code is the team's, not yours
- Do not defend, first understand the question
- Answer every comment with one of three:
  - **Keep**: "I'll leave it, because..."
  - **Change**: "Good catch, fixed."
  - **Ask**: "Can you explain what you mean?"

---

<!-- .slide: id="exercise" -->

### Exercise, step 1: be the reviewer (5 min)

Review this code. No AI. Write 2 review comments in the chat: use the levels and the good-comment rules. Don't press Enter yet.

```js
function countEven(numbers) {
  let count = 0;
  for (let i = 1; i < numbers.length; i++) {
    if (numbers[i] % 2 === 0) {
      count = count + 1;
    }
  }
}
```

---

Exercise, step 1: "go", send your comments

I will read some aloud. Listen for: is it specific, about the code, and respectful?

---

Reveal: two bugs, both level 1

- `i` starts at `1`, so the first number is never checked
- There is no `return`, so the function gives back `undefined`

---

### Exercise, step 2: be the author (4 min)

You wrote `countEven`. A reviewer gave you this comment:

> "Does the loop skip the first element? I think `i` should start at `0`."

Answer in the chat with **keep**, **change**, or **ask**, plus one sentence. Then "go".

---

<!-- .slide: id="self-review" -->

# Self-review

---

### Self-review is peer review, aimed at yourself

Before you hand over your code, be your own first reviewer.

- Use the same levels: correctness, edge cases, readability, style
- You see what you meant, not what you wrote
- Test with the boring inputs: `0`, `[]`, `undefined`
- Take a break first, and explain the code out loud (rubber ducking)

---

Try it: self-review this code in 1 minute

Type your findings in the chat, then "go".

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

# AI as a second reviewer

---

### Human first, then AI

- Do your own review first
- Then ask AI, and compare
- If AI goes first, you stop thinking and start agreeing

---

### Use it, and check it

- Good at: common bugs, simpler versions, alternatives, tone of a comment
- Not good at: knowing your intent, and it can sound confident and be wrong

You are the reviewer. AI is a second opinion. Sort each AI point into keep, change, or ask.

---

### Prompt suggestions

- "If I submitted this to a code review, what would be the top 3 concerns?"
- "What edge cases does this function not handle?"
- "Is this comment polite and specific? Suggest a better wording."

---

### Homework

Use code from your final project:

1. Swap code with a teammate (or a classmate in the course chat) and review each other's code: 2 comments, keep / change / ask
2. Self-review your own code and write down your findings first
3. Ask AI for a review
4. Note: what did AI catch that you missed? What did you catch that AI missed?

---

<!-- .slide: id="wrap-up" -->

### Wrap-up (3 min)

Different checks catch different problems: <mark>**self-review**</mark>, <mark>**testing**</mark>, <mark>**peer review**</mark>, <mark>**AI**</mark>. They add up, they do not replace each other.

Last question. Type your answer in the chat, then "go":

**What is the one thing you will check in your own code before you share it?**

Examples: empty inputs, loop start and end, unclear names, magic numbers.

---

Additional Resources:

<!-- .slide: style="font-size:80%" -->

* [Why you need a self review of your code](https://medium.com/bitdatatechie/why-you-need-a-self-review-of-your-code-4ea057f428fa)
* [How to review code effectively: A GitHub staff engineer's philosophy](https://github.blog/developer-skills/github/how-to-review-code-effectively-a-github-staff-engineers-philosophy/)
* [How to do a code review](https://google.github.io/eng-practices/review/reviewer/)
* [Code Review good practices: guide for beginners](https://medium.com/transparent-data-eng/good-practices-of-code-review-guide-for-beginners-8c084cd70be3)
* [Review your own pull requests](https://patrickdinh.medium.com/review-your-own-pull-requests-5634cad10b7a)
* [Empathy and code reviews](https://medium.com/@RoxSWEngineering/empathy-and-code-reviews-fde4e394184d)
