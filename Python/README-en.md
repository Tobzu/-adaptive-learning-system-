# Adaptive Learning System

## Overview

This is an adaptive, error-driven learning system designed to help learners master new subjects through structured, goal-based lessons. The system emphasizes learning from mistakes and introduces new concepts gradually (maximum 2 per lesson).

**Key principles:**
- **Error-driven learning**: Errors are learning opportunities, not failures
- **Gradual introduction**: Maximum 2 new concepts per lesson
- **Flexible goals**: Learners choose their own learning path
- **Study mode**: No immediate solutions—learners develop understanding through guided error correction

---

## Core Philosophy

### Study Mode

The system operates in "study mode," which means:

1. **Error identification without solutions**: When learners submit code/work, the AI identifies errors by line number and type only—no immediate solutions
2. **Guided correction**: Learners correct their own work based on error hints
3. **Understanding through iteration**: Only after error-free submission (or explicit request) does the AI provide explanations
4. **Concept limitation**: Only previously introduced concepts may be used

### Error Classification

All errors are classified into four types:

- **Syntax**: Typos, missing punctuation, wrong operators
- **Structure**: Wrong order of blocks, misplaced definitions, incorrect nesting
- **Logic**: Correct syntax but wrong meaning, infinite loops, calculation errors
- **Input**: Missing validation, unhandled exceptions, type conversion errors

---

## How to Use This System

### For Learners

**1. Session Start (2 minutes)**

At the beginning of each session, define:
- **Main goal**: What do you want to achieve today?
- **Learning goal**: What concept do you want to understand?
- **Time frame**: How much time do you have? (recommended: max 90 minutes)

**2. Learning Phase (60-80 minutes)**

Work through lessons (L##), reviews (W##), or tests (T##):

- **L## (Learning lessons)**: Introduce max 2 new concepts
- **W## (Review lessons)**: Practice and combine known concepts
- **T## (Test lessons)**: Assess mastery of all concepts in a goal

**3. Reflection (5-10 minutes)**

Answer reflection questions:
- What was difficult today? Why?
- What did you do well?
- Which strategy helped you?
- Where else could you apply this?
- What should we focus on next time?

### For AI Systems

When implementing this system, the AI must:

1. **Before each response, check:**
   - Am I in study mode?
   - Am I only mentioning errors, not solutions?
   - Am I using line numbers + error type?
   - Am I respecting the command limit (max 2 new)?
   - Am I documenting correctly?

2. **When learner submits work:**
   - Output complete code with line numbers
   - List errors: `Line X – [Error type]` (no explanation)
   - Wait for learner to correct
   - After error-free submission: Provide feedback and next steps

3. **When introducing new concepts:**
   - Explain at the beginning of the lesson
   - Provide mini-examples (not solutions to current task)
   - Indicate where they'll be used later

---

## File Structure

### Core Configuration Files

- **readme-config.json**: Machine-readable configuration of all rules
- **teaching-plan.json**: Goals (G##), lessons (L##, W##, T##), command tracker
- **error-plan.md**: Definition of error levels and error types

### Tracking Files (Personal—Exclude from Publication)

- **learning-log.json**: Session history with reflections
- **progress.json**: Goal status, error analytics, streaks
- **error-history.json**: Personal error history and triggers

### Reference Files

- **cheat-sheet.md**: Commands and concepts already learned
- **programs.txt**: Code versions from each lesson

---

## Adapting to New Subjects

This system can be adapted to any subject by:

1. **Defining goals (G##)**: Each goal represents a concrete project or milestone
2. **Breaking down skills**: Identify the smallest learnable units (commands, concepts, techniques)
3. **Creating lesson types**:
   - L## for introducing max 2 new skills
   - W## for combining known skills
   - T## for testing all skills in a goal

4. **Maintaining the command limit**: Never introduce more than 2 new concepts per lesson

### Example Adaptations

**Programming (Python, JavaScript, etc.)**
- Goals: "Build a calculator", "Create a menu system"
- Commands: `while`, `if`, `input`, `print`, `def`, `return`

**Language Learning (Esperanto, Spanish, etc.)**
- Goals: "Describe daily routine", "Order food in a restaurant"
- Commands: verb conjugations, vocabulary sets, grammar structures

**Mathematics**
- Goals: "Solve quadratic equations", "Calculate derivatives"
- Commands: formulas, proof techniques, calculation methods

---

## Goal Structure

Each goal follows this format:

```json
{
  "id": "G01",
  "title": "Project Name",
  "description": "Brief description of what this goal achieves",
  "commands": {
    "skill1": false,
    "skill2": true,
    "skill3": false
  },
  "status": "not_started | in_progress | completed",
  "progress_percent": 0
}
```

**Rules:**
- A test (T##) can only be attempted when all commands are `true`
- After passing a test, the goal status becomes `completed`

---

## Lesson Structure

### L## (Learning Lessons)

**Purpose**: Introduce maximum 2 new concepts

**Structure:**
1. Explain concept with purpose and examples
2. Provide mini-example (not solution to task)
3. Assign practice task
4. Error correction phase (study mode)

**After completion**: Set new commands to `true` in all relevant goals

### W## (Review Lessons)

**Purpose**: Combine and deepen known concepts (no new concepts)

**Structure:**
1. Present task using only known commands
2. Error correction phase
3. Reflection on combinations and applications

**Can be inserted**: At any time, especially after repeated errors

### T## (Test Lessons)

**Purpose**: Assess mastery of all commands in a goal

**Prerequisites**: All commands in the goal must be `true`

**Success**: Goal status → `completed`

**Failure**: Schedule review (W##), then retest

---

## Error Levels

The system tracks errors at three levels:

- **Level 0 (Archived)**: Error no longer occurs, learner has mastered it
- **Level 1 (Observation)**: Error was corrected, learner understands it, but might recur
- **Level 2 (Active)**: Error currently occurs frequently, needs targeted practice

**Trigger rule**: After 3+ repetitions of the same error → automatic review lesson (W##)

---

## Session Structure

### 1. Session Start (2 min)
Define personal learning goals

### 2. Learning Phase (60-80 min)
Work through lessons in study mode

### 3. Success Moments (inline)
Celebrate milestones:
- **Level 1**: Small wins (error-free code on first try)
- **Level 2**: Milestones (3 tasks in a row without errors)
- **Level 3**: Module completion (all tasks mastered)

### 4. Reflection (5-10 min)
Answer metacognitive questions

### 5. Documentation
Update learning journal and progress tracking

---

## Time Management

- **Recommended session length**: 60-90 minutes
- **Break rule**: After 45 minutes → suggest 5-minute break
- **Purpose**: Avoid cognitive overload and maintain learning effectiveness

---

## Celebration System

The system celebrates progress at three levels:

**Level 1 – Small but Important**
- Error-free code on first attempt
- Self-correction without hints
- Faster solution than last time

**Level 2 – Milestone**
- 3 tasks in a row without errors
- Repeated error (level 2) solved correctly for first time
- Complete program without external help

**Level 3 – Module Completion**
- Complete module successfully finished
- All tasks mastered without critical errors

**Celebration rules:**
- Be specific (what exactly was achieved?)
- Be justified (why is this a success?)
- Show progress (comparison with before)
- Be motivating (look forward)
- NO generic praise

---

## Publishing Without Personal Data

To publish this system as a template:

1. **Remove or anonymize:**
   - `learning-log.json` (personal session histories)
   - `progress.json` (personal progress statistics)
   - `error-history.json` (personal error patterns)
   - Any files with real timestamps, names, or specific learning data

2. **Keep as templates:**
   - `README.md` (this file)
   - `readme-config.json` (configuration)
   - `teaching-plan-template.json` (with example structure)
   - `error-plan.md` (error definitions)
   - `cheat-sheet.md` (concept reference)

3. **Replace personal content with examples:**
   - Use generic timestamps: `2025-11-25T10:00:00`
   - Use example descriptions: "Example error", "Sample lesson"
   - Mark all entries as clearly labeled samples

---

## For AI Systems: Implementation Checklist

Before each response:

- [ ] Is my answer in study mode?
- [ ] Do I only mention errors, not solutions?
- [ ] Do I use line numbers + error type?
- [ ] Do I respect the command limit (max 2 new)?
- [ ] Do I document correctly?

After each lesson:

- [ ] Ask reflection questions
- [ ] Update learning-log.json
- [ ] Update progress.json
- [ ] Set commands to true in teaching-plan.json
- [ ] On success: Output celebration
- [ ] Document errors in error-history.json
- [ ] With 3+ repetitions: Schedule W##

---

## License and Usage

This system is designed to be:

- **Adaptable**: Use for any subject
- **Privacy-friendly**: No personal data in published version
- **AI-compatible**: Works with any AI system that follows the rules
- **Evidence-based**: Built on error-driven learning and spaced repetition principles

When adapting this system:
- Keep the core principles (study mode, max 2 new concepts, error-driven)
- Adjust goals and commands to your subject
- Maintain the file structure for compatibility
- Document your adaptations

---

## Contact and Contributions

This system is a template. Adapt it, improve it, share it.

**Core principle**: Learning happens through guided discovery, not immediate solutions.

---

**Version 1.0 – November 2025**
