# Digital Proficiency Kit — Learning Materials

## Overview

This repository contains **comprehensive instructional learning materials** for the Digital Proficiency Kit (DPK), specifically designed to support **novice teachers** with little or no programming experience and their students learning HTML, CSS, and JavaScript in STEAM education contexts.

**Audience:**

- **Teachers:** Novice to intermediate educators seeking ready-to-use lesson decks, step-by-step tutorials, and scaffolded teaching materials.
- **Students:** Secondary learners working through browser-based web development modules.

**Purpose:**

- Provide Marp slide decks for module overviews and individual units.
- Offer detailed tutorials with incremental code-along steps, common pitfalls, and debugging guidance.
- Supply printable student workbooks and teacher-annotated versions with timing, differentiation, and assessment notes.

---

## Repository Structure

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

## How to Use These Materials

### For Teachers

1. **Module Overview Deck:** Start with `module-XX-overview-deck.md` to understand learning outcomes, big ideas, and module sequence.
2. **Unit Decks:** Use `unit-X.Y-deck.md` for classroom presentations. Slides include:
   - Concept explanations
   - Code-along steps
   - Guided practice prompts
   - Formative checks
   - Speaker notes with timing and differentiation tips
3. **Tutorials:** Assign or work through `unit-X.Y-tutorial.md` with students. Tutorials provide:
   - Prerequisites
   - Step-by-step code implementation
   - "Why it matters" explanations
   - Common pitfall warnings
   - Quick self-checks
4. **Student Workbooks:** Print or share `unit-X.Y-student-workbook.md` for guided practice, notes, and self-assessment.
5. **Teacher Annotated Workbooks:** Use `unit-X.Y-teacher-annotated.md` for timing, answer keys, and differentiation strategies.

### For Students

- Follow unit decks during class presentations.
- Work through tutorials step-by-step, testing code in the browser.
- Complete student workbooks to reinforce concepts and reflect on learning.

### Exporting Slides

All decks are written in [Marp](https://marp.app/) Markdown format. To export to HTML, PDF, or PPTX:

**Using Marp CLI:**

```bash
npm install -g @marp-team/marp-cli
marp modules/01-introduction-to-the-web/module-deck/module-01-overview-deck.md --html --output module-01.html
marp modules/01-introduction-to-the-web/units/1.1-what-is-the-web/unit-1.1-deck.md --pdf --output unit-1.1.pdf
```

**Using VS Code with Marp extension:**

1. Install the [Marp for VS Code](https://marketplace.visualstudio.com/items?itemName=marp-team.marp-vscode) extension.
2. Open any `.md` deck file.
3. Click the Marp icon in the editor toolbar.
4. Export to HTML, PDF, or PPTX.

**Quick Open (macOS):**

```bash
open modules/01-introduction-to-the-web/module-deck/module-01-overview-deck.md
```

---

## Relationship to Other Repositories

This repository is part of the Digital Proficiency Kit ecosystem:

- **[digital-proficiency-kit](https://github.com/STEAM-C3T/digital-proficiency-kit):** Runnable code examples, tasks, and student-facing module READMEs.
- **[teacher-toolkit](https://github.com/STEAM-C3T/teacher-toolkit):** Lesson plans, assessment rubrics, module overviews, and professional development resources.
- **dpk-learning-materials** (this repo): Marp slide decks, tutorials, and workbooks for classroom instruction.

**Navigation:**

- From DPK module READMEs → link to tutorials and decks here.
- From Teacher Toolkit module overviews → link to decks and annotated workbooks here.
- From here → link to DPK for code examples and Teacher Toolkit for rubrics.

---

## Available Modules

### Module 01: Introduction to the Web

**Status:** ✅ Complete (Pilot)

- [Module Overview Deck](modules/01-introduction-to-the-web/module-deck/module-01-overview-deck.md)
- [Unit 1.1: What Is the Web?](modules/01-introduction-to-the-web/units/1.1-what-is-the-web/)
  - [Unit 1.1 Deck](modules/01-introduction-to-the-web/units/1.1-what-is-the-web/unit-1.1-deck.md)
  - [Tutorial](modules/01-introduction-to-the-web/units/1.1-what-is-the-web/tutorial/unit-1.1-tutorial.md)
  - [Student Workbook](modules/01-introduction-to-the-web/units/1.1-what-is-the-web/workbook/unit-1.1-student-workbook.md)
  - [Teacher Annotated Workbook](modules/01-introduction-to-the-web/units/1.1-what-is-the-web/workbook/unit-1.1-teacher-annotated.md)
- [Unit 1.2: Basic Structure](modules/01-introduction-to-the-web/units/1.2-basic-structure/)

### Module 02: HTML Foundations

**Status:** 🔧 In Progress

- Templates available; content development underway

### Module 03: CSS Styling & Layout

**Status:** 🔧 In Progress

- Templates available; content development underway

### Module 04: JavaScript Essentials

**Status:** 🔧 In Progress

- Templates available; content development underway

### Module 05: Data Visualization

**Status:** 📋 Planned

### Module 06: Creative Web Projects

**Status:** 📋 Planned

### Module 07: Green STEAM Challenge

**Status:** 📋 Planned

---

## Templates

Reusable templates for creating new materials are in `templates/`:

- **Marp Decks:** `module-deck-template.md`, `unit-deck-template.md`
- **Tutorials:** `tutorial-template.md`
- **Workbooks:** `student-workbook-template.md`, `teacher-annotated-template.md`

Use these as starting points for consistent formatting and structure across all modules.

---

## Accessibility & Inclusion

All materials are designed with accessibility in mind:

- Marp slides use high-contrast themes and clear fonts.
- Tutorials include text descriptions of visual diagrams.
- Student workbooks provide scaffolded note-taking areas.
- Teacher annotated versions highlight differentiation strategies for mixed-ability classrooms.

---

## Contributing

Contributions are welcome! To add or improve materials:

1. Fork this repository.
2. Use templates from `templates/` for consistency.
3. Follow naming conventions: lowercase, hyphen-separated filenames.
4. Update `CHANGELOG.md` with your changes.
5. Submit a pull request with a clear description.

For detailed contribution guidelines, see [CONTRIBUTING.md](CONTRIBUTING.md) (to be added).

---

## License

This repository is licensed under the same open-source license as the Digital Proficiency Kit. See [LICENSE](LICENSE) for details.

---

## Contact & Support

For questions, suggestions, or feedback:

- Open an issue in this repository.
- Contact the STEAM-C3T team via the main Digital Proficiency Kit repository.

---

**Last Updated:** 2025-11-18  
**Version:** 0.1.0 (Pilot — Module 01)
