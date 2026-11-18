<!-- .slide: id="lesson16" -->

# JavaScript Course - Fall 2026

Lesson 16, Thursday, 2026-11-19

---

# Final Project!

---

### Organizational info

- Individual or team of 2-3 people
  - Fill out the info in the [spreadsheet](https://docs.google.com/spreadsheets/d/1cGi8wireyajPRoPKO_gknpWSep96URCKWojU8MLKLOw/edit?usp=sharing)!
- Internal presentation date: 10.12.2026
  - You will present your project to the class
- Are you located in Hamburg? You can present at the in-person Demo Day
  - Nominate yourself

---

### Project requirements

Each project must include:

- A code-based solution using JavaScript
- A presentation and a live demo (showing a working web app or website with interactivity)

---

### Presentation 🎬

- Length: Max. 5 minutes
- Mode: Slides or Live Demonstration
- Proposed Structure:
  - Intro – What’s the project, and what problem does it solve?
  - Demo – Show the live website
  - Challenges & Learning – What went well? What was hard? What did you learn?

---

### Project Ideas 💡

- A quiz or trivia game
- A to-do list or productivity tool
- An interactive landing page or form
- A weather or news app using APIs
- Anything aligned with the course content and realistic for the timeframe

---

### Project Strategy

- Define a Minimum Viable Product (MVP)

- Create a list of tasks you'll have to do to put the MVP in place.
  - Even better: break down the tasks week by week to keep track of your progress and get help in time if you're blocked.

- Implement essential functionality, and if there's still time, implement the "nice to have" features.


---

### Last semesters

- [WhattaCook](https://github.com/katamatata/katamatata.github.io)
- [Plantastik](https://github.com/annamariaratajczak/plantastick)
- [Giphy CopyCat](https://github.com/ami-onodera/giphy)
- [Memory Game](https://github.com/TainaraCris1/Project_Memory_Game)
- [Tic-Tac-Toe](https://github.com/Amani-Maklad/Tic-Tac-Toe)

---

### More ideas

- Data visualization of the flee markets in Berlin
- Calendar for Remote work
- Grocery shopping list
- AI in the browser
- Personal Portfolio

---

### APIs

- [Berlin data](https://daten.berlin.de/datensaetze/datenberlinde-metadaten)
- [Free APIS](https://free-apis.github.io/#/browse)
- [Public APIs](https://github.com/public-apis/public-apis)

---

### AI in the browser

Latest Chrome beta can run small AI models in the browser!

```js
let model = await LanguageModel.create();
let answer = await model.prompt("Why is JavaScript awesome?");
// or detect language
let detector = await LanguageDetector.create();
let result = await detector.detect("Merci common ca va?");
```

Documentation: https://developer.chrome.com/docs/ai/built-in
