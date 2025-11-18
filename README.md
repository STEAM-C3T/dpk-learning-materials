# Digital Proficiency Kit — Learning Materials

### _STEAM: From Campus to Classroom, Crafting Tomorrow (STEAM-C3T)_

**Erasmus+ Cooperation Partnerships in School Education (KA220-SCH)**

Developed by **Tallinn University, Haapsalu College**

---

## Overview

This repository contains **comprehensive instructional learning materials** for the Digital Proficiency Kit (DPK), specifically designed to support **novice teachers** with little or no programming experience and their students learning HTML, CSS, and JavaScript in STEAM education contexts.

The materials follow the principles of **learning by making** and align with the **EU DigComp 2.2** competence framework.
All resources are classroom-ready and require only a modern web browser—no installation or external software needed.

---

## Objectives

- Provide ready-to-use slide decks, tutorials, and workbooks for classroom delivery of DPK modules.
- Support novice teachers with step-by-step guidance, common pitfalls, and differentiation strategies.
- Enable students to build practical digital skills through scaffolded practice and self-assessment.
- Offer materials that integrate coding, design, and STEAM themes with accessibility and ethical considerations.

---

## Learning Materials Structure

```
dpk-learning-materials/
  modules/
    01-introduction-to-the-web/
      module-deck/
        module-01-overview-deck.md
      units/
        1.1-what-is-the-web/
          unit-1.1-deck.md
          tutorial/
            unit-1.1-tutorial.md
          workbook/
            unit-1.1-student-workbook.md
            unit-1.1-teacher-annotated.md
        1.2-basic-structure/
          unit-1.2-deck.md
          tutorial/
            unit-1.2-tutorial.md
          workbook/
            unit-1.2-student-workbook.md
            unit-1.2-teacher-annotated.md
      assets/
        images/
        code-snippets/
    02-html-foundations/
      ...
    (Modules 03–07 follow the same pattern)
  templates/
    marp/
      module-deck-template.md
      unit-deck-template.md
    tutorials/
      tutorial-template.md
    workbooks/
      student-workbook-template.md
      teacher-annotated-template.md
  CHANGELOG.md
  README.md (this file)
```

---

## Folder Structure

```
dpk-learning-materials/
├── modules/
│   ├── 01-introduction-to-the-web/
│   ├── 02-html-foundations/
│   ├── 03-css-styling-layout/
│   ├── 04-javascript-essentials/
│   ├── 05-data-visualization/
│   ├── 06-creative-web-projects/
│   ├── 07-green-steam-challenge/
│   └── README.md
├── templates/
│   ├── marp/
│   ├── tutorials/
│   └── workbooks/
├── CHANGELOG.md
└── README.md
```

Example module folder layout:

```
modules/05-data-visualization/
├── module-deck/          # Module overview deck
├── units/
│   └── 5.1-canvas-basics/
│       ├── deck/         # Unit presentation slides
│       ├── tutorial/     # Step-by-step guide
│       └── workbook/     # Student + teacher versions
└── assets/               # Images, code snippets (if needed)
```

---

## Get Started

- Browse the [Learning Materials Structure](#learning-materials-structure) table below to find modules.
- Start with a module overview deck to understand learning outcomes and sequence.
- Use unit decks for classroom presentations, tutorials for code-along sessions, and workbooks for practice.

---

### Quick Open Tips (macOS)

Open any deck directly in your default Markdown viewer or browser:

```zsh
# Replace the path with any deck file you want to open
open modules/01-introduction-to-the-web/module-deck/module-01-overview-deck.md
open modules/05-data-visualization/units/5.1-canvas-basics/deck/unit-5.1-deck.md
open modules/07-green-steam-challenge/module-deck/module-07-deck.md
```

**Exporting Slides to PDF/HTML/PPTX:**

All decks use [Marp](https://marp.app/) Markdown format.

```bash
npm install -g @marp-team/marp-cli
marp modules/05-data-visualization/module-deck/module-05-deck.md --pdf --output module-05.pdf
```

Or use the [Marp for VS Code](https://marketplace.visualstudio.com/items?itemName=marp-team.marp-vscode) extension for one-click export.

---

## Pedagogical Approach

The materials are built upon three principles:

1. **Create to learn** – digital skills grow through making, testing, and sharing artefacts.
2. **Integrate to understand** – web coding links naturally with mathematics, art, and science.
3. **Reflect to improve** – teachers and learners assess their progress through authentic outcomes rather than abstract tests.

---

## Technical Requirements

- Modern web browser (Chrome, Firefox, Edge, or Safari).
- Optional: [Marp CLI](https://github.com/marp-team/marp-cli) or [Marp for VS Code](https://marketplace.visualstudio.com/items?itemName=marp-team.marp-vscode) for exporting slides.
- All materials are plain Markdown—no build tools or dependencies required.

---

## Related Repositories

The Learning Materials repository is part of a three-repository ecosystem:

### **1. [Digital Proficiency Kit](https://github.com/STEAM-C3T/digital-proficiency-kit)**

Runnable code examples, tasks, and student-facing module guides.

### **2. [Teacher Toolkit](https://github.com/STEAM-C3T/teacher-toolkit)**

Lesson plans, assessment rubrics, module overviews, and professional development resources.

### **3. Learning Materials** (this repository)

Comprehensive instructional materials specifically designed for **novice teachers with little or no programming experience**, including:

- **Marp slide decks** for module overviews and unit lessons (ready to present in class)
- **Step-by-step tutorials** with code-along examples, common pitfalls, and debugging guidance
- **Student workbooks** with scaffolded practice, note-taking areas, and self-assessment
- **Teacher-annotated workbooks** with timing estimates, differentiation strategies, misconception alerts, and answer keys

**Navigation:**

- From DPK module READMEs → links to Learning Materials decks and tutorials
- From Teacher Toolkit lesson plans → links to Learning Materials for classroom-ready presentations
- From Learning Materials → links back to DPK for code examples and Teacher Toolkit for assessment rubrics

---

## Accessibility & Inclusion

All materials are designed with accessibility in mind:

- Marp slides use high-contrast themes and clear fonts.
- Tutorials include text descriptions of visual diagrams.
- Student workbooks provide scaffolded note-taking areas.
- Teacher annotated versions highlight differentiation strategies for mixed-ability classrooms.

---

## Contribution and Collaboration

---

## Learning Materials Structure

| Module                                                              | Focus                                  | Example Outcome                               |
| ------------------------------------------------------------------- | -------------------------------------- | --------------------------------------------- |
| [1. Introduction to the Web](./modules/01-introduction-to-the-web/) | How websites work, file structure      | Simple webpage using semantic HTML            |
| [2. HTML Foundations](./modules/02-html-foundations/)               | Content hierarchy, accessibility       | Student topic/portfolio page                  |
| [3. CSS Styling & Layout](./modules/03-css-styling-layout/)         | Typography, colours, responsive design | Styled and responsive site                    |
| [4. JavaScript Essentials](./modules/04-javascript-essentials/)     | Variables, events, DOM manipulation    | Interactive UI component                      |
| [5. Data Visualization](./modules/05-data-visualization/)           | Displaying data with charts/canvas     | Small data chart/visual with accessible table |
| [6. Creative Web Projects](./modules/06-creative-web-projects/)     | Art and computation                    | Digital poster or generative piece            |
| [7. Green STEAM Challenge](./modules/07-green-steam-challenge/)     | Sustainable innovation with code       | Small SDG‑themed mini‑app                     |

Each module includes:

- **Module Overview Deck:** Learning outcomes, big ideas, and module sequence
- **Unit Decks:** Classroom presentation slides with concept explanations, code-along steps, and formative checks
- **Tutorials:** Step-by-step code implementation with common pitfalls and debugging guidance
- **Student Workbooks:** Guided practice, note-taking areas, and self-assessment
- **Teacher Annotated Workbooks:** Answer keys, timing estimates, differentiation strategies, and assessment notes

### Detailed Unit Links

#### Module 01

- [Module Overview Deck](modules/01-introduction-to-the-web/module-deck/module-01-overview-deck.md)
- Unit 1.1: What Is the Web?
  - [Deck](modules/01-introduction-to-the-web/units/1.1-what-is-the-web/unit-1.1-deck.md)
  - [Tutorial](modules/01-introduction-to-the-web/units/1.1-what-is-the-web/tutorial/unit-1.1-tutorial.md)
  - [Student Workbook](modules/01-introduction-to-the-web/units/1.1-what-is-the-web/workbook/unit-1.1-student-workbook.md)
  - [Teacher Workbook](modules/01-introduction-to-the-web/units/1.1-what-is-the-web/workbook/unit-1.1-teacher-annotated.md)
- Unit 1.2: Basic Structure (deck, tutorial, student + teacher workbooks)

#### Module 02

- [Module Overview Deck](modules/02-html-foundations/module-deck/module-02-overview-deck.md)
- Unit 2.1: Building Content (deck, tutorial, student + teacher workbooks)
- Unit 2.2: Structuring for Access (deck, tutorial, student + teacher workbooks)

#### Module 03

- [Module Overview Deck](modules/03-css-styling-layout/module-deck/module-03-overview-deck.md)
- Unit 3.1: CSS Fundamentals (deck, tutorial, student + teacher workbooks)
- Unit 3.2: Responsive Layouts (deck, tutorial, student + teacher workbooks)

#### Module 04

- [Module Overview Deck](modules/04-javascript-essentials/module-deck/module-04-overview-deck.md)
- Unit 4.1: JavaScript Basics (deck, tutorial, student + teacher workbooks)
- Unit 4.2: DOM Manipulation (deck, tutorial, student + teacher workbooks)

#### Module 05

- [Module Overview Deck](modules/05-data-visualization/module-deck/module-05-deck.md)
- Unit 5.1: Canvas Basics
  - [Deck](modules/05-data-visualization/units/5.1-canvas-basics/deck/unit-5.1-deck.md)
  - [Tutorial](modules/05-data-visualization/units/5.1-canvas-basics/tutorial/unit-5.1-tutorial.md)
  - [Student Workbook](modules/05-data-visualization/units/5.1-canvas-basics/workbook/unit-5.1-student-workbook.md)
  - [Teacher Workbook](modules/05-data-visualization/units/5.1-canvas-basics/workbook/unit-5.1-teacher-annotated.md)

#### Module 06

- [Module Overview Deck](modules/06-creative-web-projects/module-deck/module-06-deck.md)
- Unit 6.1: Generative Art
  - [Deck](modules/06-creative-web-projects/units/6.1-generative-art/deck/unit-6.1-deck.md)
  - [Tutorial](modules/06-creative-web-projects/units/6.1-generative-art/tutorial/unit-6.1-tutorial.md)
  - [Student Workbook](modules/06-creative-web-projects/units/6.1-generative-art/workbook/unit-6.1-student-workbook.md)
  - [Teacher Workbook](modules/06-creative-web-projects/units/6.1-generative-art/workbook/unit-6.1-teacher-annotated.md)

#### Module 07

- [Module Overview Deck](modules/07-green-steam-challenge/module-deck/module-07-deck.md)
- Unit 7.1: Sustainability Mini‑App
  - [Deck](modules/07-green-steam-challenge/units/7.1-green-mini-app/deck/unit-7.1-deck.md)
  - [Tutorial](modules/07-green-steam-challenge/units/7.1-green-mini-app/tutorial/unit-7.1-tutorial.md)
  - [Student Workbook](modules/07-green-steam-challenge/units/7.1-green-mini-app/workbook/unit-7.1-student-workbook.md)
  - [Teacher Workbook](modules/07-green-steam-challenge/units/7.1-green-mini-app/workbook/unit-7.1-teacher-annotated.md)

> All seven modules now have complete instructional sets (overview deck, unit deck(s), tutorial, student workbook, teacher annotated workbook) following the shared template structure.

---

Educators and partners are encouraged to adapt, translate, and extend the materials.
Feedback, new lesson ideas, and content improvements can be shared through Issues or Pull Requests in this repository.

**Guidelines:**

- Use templates from `templates/` for consistency.
- Follow naming conventions: lowercase, hyphen-separated filenames.
- Update `CHANGELOG.md` with your changes.

---

## License

This repository is licensed under the same open-source license as the Digital Proficiency Kit. See [LICENSE](LICENSE) for details.

---

**Last Updated:** 2025-11-18  
**Version:** 1.0.0 (Modules 01–07 Complete)
