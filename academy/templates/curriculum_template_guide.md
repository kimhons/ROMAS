# Radiation Oncology Academy: Curriculum Development Guide

## 1. Introduction

This document outlines the standard template, pedagogical rationale, and development guidelines for creating curriculum content for the Radiation Oncology Academy. Its purpose is to ensure consistency, quality, and pedagogical effectiveness across all modules, including future development by different agents (e.g., for the Diagnostic Physics curriculum).

Adherence to this guide is crucial for maintaining the high standards of detail, practical relevance, and clinical integration expected in the Academy's materials.

## 2. Overall Philosophy

The curriculum aims to provide a comprehensive learning experience for medical physics residents and professionals. It blends foundational knowledge with practical application, clinical relevance, and critical assessment. The structure emphasizes active learning, problem-solving, and engagement with authoritative reference materials.

## 3. Standard Subsection Template

Each subsection within the curriculum (e.g., Section 1.1, Section 1.2) should ideally contain the following components, presented in separate Markdown files within the corresponding section directory (e.g., `/curriculum/section_1_1/`).

**File Naming Convention:** `[component_type]_[section_number].md` (e.g., `key_concepts_1_1.md`, `deep_dive_tg51_1_1.md`).

**Content Formatting:**
*   Use **Markdown** for all text content.
*   Employ **detailed bullet points** for explanations and lists. Avoid dense paragraphs; break down information logically.
*   Use standard **LaTeX syntax** enclosed in single dollar signs (`$...$`) for inline equations and double dollar signs (`$$...$$`) for display equations. Ensure equations are correctly formatted for rendering by MathJax or KaTeX.
*   Maintain a professional and informative tone.
*   Ensure all content provides **practical guidance** and **clinical relevance** where applicable.

### 3.1. Key Concepts (`key_concepts_X_Y.md`)

*   **Purpose (Pedagogy):** To establish a strong theoretical foundation for the subsection's topic. This component explains the core principles, definitions, theories, and fundamental equations.
*   **Instructions:**
    *   Identify the essential concepts learners must grasp.
    *   Explain each concept clearly and concisely using detailed bullet points.
    *   Include relevant fundamental equations (using LaTeX).
    *   Provide necessary background or context.
    *   Focus on clarity and accuracy.
    *   Where applicable, briefly mention clinical significance.

### 3.2. Clinical Scenarios (`clinical_scenarios_X_Y.md`)

*   **Purpose (Pedagogy):** To bridge the gap between theory and practice. These scenarios illustrate how the key concepts are applied in real-world clinical settings, enhancing understanding and relevance.
*   **Instructions:**
    *   Develop realistic clinical situations related to the subsection topic.
    *   Describe the scenario, the challenge or task involved, and how the concepts are used to address it.
    *   Use detailed bullet points to outline the scenario and its resolution.
    *   Focus on practical decision-making and problem-solving.
    *   Include multiple diverse scenarios if appropriate.

### 3.3. Multiple Choice Questions (MCQs) (`mcqs_X_Y.md`)

*   **Purpose (Pedagogy):** To provide learners with self-assessment opportunities to check their comprehension of the key concepts.
*   **Instructions:**
    *   Create a set of relevant MCQs (typically 5-10) covering the core concepts.
    *   Ensure questions are clear, unambiguous, and have one correct answer.
    *   Include plausible distractors.
    *   Format questions clearly (e.g., numbered list).
    *   **Do not include answers here.** Answers belong in the `solutions_X_Y.md` file.

### 3.4. Deep Dives (References) (`deep_dive_[ReferenceName]_X_Y.md`)

*   **Purpose (Pedagogy):** To guide learners through essential, authoritative reference materials (e.g., AAPM TG reports, IAEA documents, NCRP reports). These summaries extract key recommendations, methodologies, and practical guidance.
*   **Instructions:**
    *   Based on the specified reference document(s) for the subsection.
    *   Thoroughly review the source document.
    *   Summarize the most critical sections, recommendations, data tables, and practical procedures using detailed bullet points.
    *   Directly cite or reference specific sections/tables from the source document where appropriate.
    *   Include key equations (using LaTeX) or important data presented in the report.
    *   Focus on extracting actionable information and practical implementation guidance.
    *   Create a separate file for each major reference document.

### 3.5. Activities (`activities_X_Y.md`)

*   **Purpose (Pedagogy):** To promote active learning and application of knowledge through hands-on tasks or exercises.
*   **Instructions:**
    *   Design 1-3 activities that require learners to apply concepts or procedures.
    *   Examples: Data analysis tasks, calculation exercises, simulation setup descriptions, QA procedure outlines.
    *   Provide clear instructions for each activity.
    *   Specify any required data or tools (if applicable).
    *   **Do not include solutions here.** Solutions belong in the `solutions_X_Y.md` file.

### 3.6. Worked Examples (`worked_examples_X_Y.md`)

*   **Purpose (Pedagogy):** To demonstrate problem-solving techniques and calculations step-by-step, reinforcing understanding and building confidence.
*   **Instructions:**
    *   Select 1-3 representative problems related to the subsection topic.
    *   Present the problem statement clearly.
    *   Provide a detailed, step-by-step solution using detailed bullet points.
    *   Show all calculations (using LaTeX for equations).
    *   Explain the reasoning behind each step.

### 3.7. Assessment (`assessment_X_Y.md`)

*   **Purpose (Pedagogy):** To provide a more formal evaluation of the learner's understanding and ability to apply the knowledge from the subsection.
*   **Instructions:**
    *   Create a set of assessment questions (can include MCQs, short answers, calculation problems, scenario analysis).
    *   Ensure questions cover the breadth and depth of the subsection's content.
    *   Aim for a higher level of synthesis or application than the initial MCQs.
    *   Format questions clearly.
    *   **Do not include answers here.** Answers belong in the `solutions_X_Y.md` file.

### 3.8. Protocol / Procedure (`protocol_X_Y.md`)

*   **Purpose (Pedagogy):** To provide practical, step-by-step guidance on performing specific clinical tasks, QA procedures, or workflows relevant to the subsection.
*   **Instructions:**
    *   Identify a key protocol or procedure related to the topic.
    *   Outline the procedure in a clear, sequential, step-by-step format using detailed bullet points or numbered lists.
    *   Include necessary details like equipment, settings, tolerances, action levels, and documentation requirements.
    *   Base the protocol on established guidelines (e.g., TG reports) or common clinical practice.

### 3.9. Solutions (`solutions_X_Y.md`)

*   **Purpose (Pedagogy):** To provide feedback and allow learners to check their work from the MCQs, Activities, and Assessment components.
*   **Instructions:**
    *   Provide clear answers and explanations for all questions/tasks in the `mcqs_X_Y.md`, `activities_X_Y.md`, and `assessment_X_Y.md` files.
    *   For calculations or complex activities, show the steps involved in reaching the solution.
    *   Organize solutions clearly, referencing the original question or activity number.

### 3.10. Quality Assurance (QA) Review (`quality_review_X_Y.md`)

*   **Purpose (Pedagogy & Process):** To ensure the accuracy, completeness, clarity, and pedagogical effectiveness of all components within the subsection before finalization.
*   **Instructions:**
    *   This file acts as a checklist and record of the QA process.
    *   Create a checklist covering key quality aspects for each component file (e.g., Accuracy, Clarity, Completeness, Formatting (Markdown, LaTeX), Clinical Relevance, Practicality, Consistency with Guide).
    *   The agent developing the content should perform an initial self-review against the checklist.
    *   Ideally, a separate review (by another agent or the user) should be conducted.
    *   Record the review date, reviewer, findings, and confirmation that all issues have been addressed.
    *   This step should be performed *after* all other components for the subsection are drafted.

## 4. Development Process

1.  **Understand Scope:** Clearly define the topic and scope of the subsection based on the overall curriculum plan.
2.  **Gather References:** Identify and obtain the key reference documents (TG reports, etc.).
3.  **Draft Components:** Create drafts for each component file (Key Concepts, Deep Dives, MCQs, etc.) following the instructions above.
4.  **Self-Review:** Perform an initial QA check against the guidelines.
5.  **Generate QA File:** Create the `quality_review_X_Y.md` file and document the self-review.
6.  **Submit for Review:** Present the drafted components and QA file for external review (if applicable).
7.  **Incorporate Feedback:** Address any feedback or required revisions.
8.  **Finalize:** Update the QA file to reflect completion and finalize all component files.
9.  **Update Tracking:** Ensure the main `overall_curriculum_tracking.md` is updated with the correct status and file paths.
10. **Commit:** Commit all new/updated files to the repository.

## 5. Conclusion

By following this guide, we can collaboratively build a high-quality, consistent, and effective curriculum for the Radiation Oncology Academy. Clear communication and adherence to these standards are essential for success, especially when multiple agents contribute to the project.

