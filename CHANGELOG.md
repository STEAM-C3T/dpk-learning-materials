# Changelog

All notable changes to the Digital Proficiency Kit Learning Materials will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

### Added - 2025-11-18

**Repository Scaffolding & Module 01 Pilot**

- Created comprehensive main `README.md` with repository overview, structure, usage instructions, and ecosystem links.
- Created template files for consistent content creation:
  - `templates/marp/module-deck-template.md`: Module overview deck template
  - `templates/marp/unit-deck-template.md`: Unit lesson deck template
  - `templates/tutorials/tutorial-template.md`: Step-by-step tutorial template
  - `templates/workbooks/student-workbook-template.md`: Student workbook template
  - `templates/workbooks/teacher-annotated-template.md`: Teacher annotated workbook template with timing, differentiation, and assessment notes

**Module 01: Introduction to the Web (Pilot Complete)**

- Module Overview Deck:

  - `modules/01-introduction-to-the-web/module-deck/module-01-overview-deck.md`: Full Marp slide deck with learning outcomes, big ideas, demonstration, assessment criteria, accessibility spotlight, and speaker notes for teachers

- Unit 1.1: What Is the Web?

  - `modules/01-introduction-to-the-web/units/1.1-what-is-the-web/unit-1.1-deck.md`: Lesson deck covering internet vs. web, client-server model, HTML/CSS/JavaScript roles, with guided practice and formative checks
  - `modules/01-introduction-to-the-web/units/1.1-what-is-the-web/tutorial/unit-1.1-tutorial.md`: Step-by-step tutorial exploring webpages with browser DevTools, including debugging tips and practice variations
  - `modules/01-introduction-to-the-web/units/1.1-what-is-the-web/workbook/unit-1.1-student-workbook.md`: Student workbook with learning objectives, concept notes, guided practice scaffolds, self-assessment, and reflection prompts
  - `modules/01-introduction-to-the-web/units/1.1-what-is-the-web/workbook/unit-1.1-teacher-annotated.md`: Teacher version with timing estimates, common misconceptions, differentiation strategies, answer keys, and accessibility accommodations

- Unit 1.2: Basic HTML Structure (Content created; see files for details)
  - Deck, tutorial, student workbook, and teacher annotated workbook following same structure as Unit 1.1

**Cross-Repository Integration**

- Added references to this repository in:
  - `digital-proficiency-kit` main README and module READMEs
  - `teacher-toolkit` main README and module overviews

**Infrastructure**

- Established folder taxonomy for modules 01–07 (pilot complete for Module 01; structure ready for 02–07)
- Documented Marp export workflow in README (CLI and VS Code extension)

**Author:** Digital Proficiency Kit Team  
**Target Audience:** Novice teachers with little/no programming experience and secondary students

---

# Changelog

All notable changes to the Digital Proficiency Kit Learning Materials repository will be documented in this file.

---

## [0.2.0] - 2025-11-18

### Added

- **Module 02: HTML Foundations** — Complete structure
  - Module overview deck with concise slides
  - Unit 2.1: Building Content (deck, README, placeholders for tutorial and workbooks)
  - Unit 2.2: Structuring for Access (deck, README, placeholders for tutorial and workbooks)
- **Module 03: CSS Styling & Layout** — Complete structure
  - Module overview deck with concise slides
  - Unit 3.1: CSS Fundamentals (deck, README, placeholders for tutorial and workbooks)
  - Unit 3.2: Responsive Layouts (deck, README, placeholders for tutorial and workbooks)
- **Module 04: JavaScript Essentials** — Complete structure
  - Module overview deck with concise slides
  - Unit 4.1: JavaScript Basics (deck, README, placeholders for tutorial and workbooks)
  - Unit 4.2: DOM Manipulation (deck, README, placeholders for tutorial and workbooks)

### Changed

- Updated main README with links to all Modules 02–04 materials
- Updated version to 0.2.0 to reflect expanded module coverage
- All new slide decks follow concise, slide-appropriate format (key points only, details in tutorials)

---

## [0.1.0] - 2025-11-18

### Initial Release

- Repository created with Module 01 pilot materials
- Templates established for consistent content creation across future modules
- Integration with Digital Proficiency Kit and Teacher Toolkit repositories

---

<!--
Changelog Maintenance Notes for Contributors:
- Add new entries under [Unreleased] as you work.
- When releasing a version, move [Unreleased] items to a new version section with date.
- Use categories: Added, Changed, Deprecated, Removed, Fixed, Security.
- Reference file paths and briefly describe content.
-->
