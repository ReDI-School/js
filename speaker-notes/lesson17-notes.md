# Lesson 17 speaker notes: Peer Review

50 min, Zoom. All exercises run in the chat: students type, wait, then send together on "go".

Timing: warm-up 5, peer review 18, exercise 10, self-review 5, AI 6, wrap-up 3. Intro 3.

---

## Intro (3 min)

**Title slide**
- Today is about reviewing code, not judging people. Say that early.

**Today's objective**
- Four things you can do at the end: comment, respond, check your own code, use AI.
- Point out: the last one says "without letting it think for you". We come back to it.

**How we work today: the chat**
- Explain the rule once: type, don't press Enter, wait for "go".
- Why: if one person answers first, everyone copies. This keeps it honest.
- Tip: if the chat is quiet, call a name and ask them to read their answer aloud.

**Agenda**
- Just read the blocks and times. No recap of Lesson 16 today.

**Experiment note**
- One sentence: this is a new format, tell me what works and what doesn't.

---

## Warm-up (5 min)

**Warm-up title**
- "No theory yet. You already know how to read code. Just react."

**Look at this code** (`numFriends ** ticketPrice`)
- Give them 1 minute to type. Then "go".
- Read 3 or 4 answers aloud. Most will say names or nothing at all.
- Don't reveal yet.

**Reveal**
- `2 ** 2` and `2 * 2` are both 4. The output looks right.
- Run it with 3 friends in your head: 9 instead of 6.
- Key message: "It runs" is not "it is right". Tests with lucky numbers don't catch it. A second pair of eyes might.
- "You just did a peer review." Let that land.

---

## Peer review (18 min)

**Peer review definition**
- Plain version: someone else reads your code before it counts as done.
- It's the code that gets reviewed. Not you.

**Why peer review?**
- Go through the four labels, one sentence each:
  - Cost: a bug found now costs minutes. A bug found by a customer costs days.
  - Quality: clearer code is easier to change later.
  - Culture: knowledge spreads.
  - Mindset: both sides learn.
- The second job of review is sharing knowledge. A reviewer learns how the code works. The author learns how a reader sees it. Nobody is the only person who understands a part of the code.
- Analogy: a flight crew. The co-pilot doesn't only catch the pilot's mistakes. Both always know what the plane is doing. A review is the moment two people agree on what the code does.
- Background: reviews started in the 1970s as formal inspections to find defects. Today's lightweight reviews (pull requests) are valued just as much for spreading knowledge.

**What do reviewers look at?**
- Four levels, in this order. The order matters: don't argue about spaces while the code is wrong.
- Analogy: checking a house. First does it stand? Then does the door open? Then is it easy to live in? Paint colour comes last.

**Which level is this?** (off-by-one loop)
- Give them 30 seconds. They type 1 to 4, then "go".
- Count the answers out loud. Most should say 1.

**Level 1: off-by-one**
- `<=` goes one step too far. Index 3 doesn't exist.
- Analogy: fence posts. 3 gaps need 4 posts, but 3 posts need only 2 gaps. Counting from 0 or 1 is where it goes wrong.

**Which level is this?** (`average`)
- Same routine. Expect mixed answers, that's fine.

**Level 2: edge cases**
- Empty list gives `0 / 0`, which is `NaN`.
- The good move is to ask: "What should happen here?" Don't just say "fix it".
- Analogy: the average of no exam results isn't 0. There is simply no answer.

**Which level is this?** (`f(x)`)
- Quick. Most will see the name.

**Level 3: readability**
- `f` says nothing. `0.9` is a magic number: a price tag without a label.
- Show the fixed version. Same code, but a reader understands it without asking.

**How to write a good comment**
- Four rules. Say the first one slowly: talk about the code, not the person.
- Analogy: a coach vs a critic. Both see the problem. The coach points to what to do next.

**Bad comment vs good comment**
- Read one pair aloud, let them read the other.
- Point out the pattern: the better comment names the line, explains the effect, and asks a question.

**Your turn: rewrite this comment**
- 1 minute in the chat, then "go".
- Pick two answers. Ask the class: is it specific? Is it about the code? Does it invite an answer?

**Receiving feedback**
- Short slide. The hard part of review is receiving, not giving.
- Keep, change, ask: like replying to an email. Say yes, say no with a reason, or ask a question.
- "It's the team's code" takes the sting out.

---

## Exercise (10 min)

**Step 1: be the reviewer** (5 min)
- Read the instructions aloud. No AI.
- Two comments each, typed but not sent. Give 3 minutes.

**"Go", send your comments**
- Read 3 or 4 aloud. Praise the specific ones.
- Check each against: specific, about the code, respectful.

**Reveal: two bugs**
- Loop starts at 1, so the first number is skipped.
- No `return`: the function gives back `undefined`.
- Ask: who found both? Who found one? Both are fine.

**Step 2: be the author** (4 min)
- Now they switch sides. They answer a good comment with keep, change, or ask plus one sentence.
- Most will say "change". Ask one student who answered "ask" what they would ask. That's a healthy habit.
- Link back: remember the "it's the team's code" slide.

---

## Self-review (5 min)

**Self-review title**
- "Same skill. Now aimed at your own code."

**Self-review is peer review, aimed at yourself**
- You already know the four levels. Use them on yourself.
- Analogy: proofreading your own essay. Your brain reads what you meant, not what you wrote.
- Rubber ducking: explain the code to a rubber duck, line by line. Many bugs show up while you talk.
- Test with boring inputs: `0`, empty list, `undefined`.

**Try it: `findMax`**
- 1 minute. Type findings, then "go".
- Hint if nobody finds it: what does it return for all negative numbers?

**Reveal**
- `max` starts at 0, so `[-5, -2, -9]` returns 0. Level 1.
- Empty list: also 0. Is that intended? Level 2.
- Fix: start with the first element and decide what happens for an empty list.

---

## AI as a second reviewer (6 min)

**AI title**
- "AI is a second reviewer. Not the first."

**Human first, then AI**
- Do your own review first, then compare.
- If AI goes first you stop thinking and start agreeing. This is called anchoring.
- Analogy: ask a friend for directions after you've looked at the map, not before.

**Use it, and check it**
- Good at: common bugs, simpler versions, alternatives, wording of a comment.
- Not good at: your intent. It can sound sure and be wrong.
- Analogy: a confident new colleague who hasn't read your project. Useful, but check the work.
- Same keep, change, ask routine for every AI point.

**Prompt suggestions**
- Read one aloud. Say: ask for the top 3 concerns, not "is it good?". A narrow question gets a better answer.

**Homework**
- Four steps: swap with a teammate, self-review, AI review, compare.
- The compare step is the learning: what did the AI catch that you missed, and the reverse?

---

## Wrap-up (3 min)

**Wrap-up slide**
- Architect view: review is one layer in a chain of checks. Self-review, then linters and tests, then peer review, then CI, then production monitoring.
- This is called "shift left": catch problems as early as possible on the timeline. Each layer is cheaper than the one after it, and each catches different bugs.
- Analogy: Swiss cheese. Every slice has holes. Stack enough slices and the holes don't line up.
- The four bold terms: they add up, they don't replace each other.
- Last question to the chat: one thing you will check in your own code before sharing. Read a few aloud, then thank them.

**Additional resources**
- Say they're optional. Recommend the GitHub and Google guides first.

---

## If you run late

- Drop the `f(x)` snippet first.
- Then shorten the exercise: skip step 2, ask for keep, change, ask in a single sentence in the wrap-up.
- Never skip the warm-up. It sets up the idea that someone else's eyes find different bugs.
