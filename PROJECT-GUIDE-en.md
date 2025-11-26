# Project Guide – Adaptive Learning System

## Overview

This guide explains how to use, adapt, and improve the Adaptive Learning System for any subject. It documents the development process, best practices, and source management that made this system work.

First, you need to upload the files:
Readme.md, cheat-sheet, error-history, error pla, learning log, progress, readme-config, and teaching-plan to the project/space.

### IMPORTANT:
You do not need to have any programming knowledge. If you notice any areas for improvement during a lesson, type “Todo: problem xy.” At the end, say that you want to incorporate all improvements. The LMM will provide the modified/new block that you can insert/change => upload new file.

---

## Table of Contents

1. [How This System Works](#how-this-system-works)
2. [How We Developed It](#how-we-developed-it)
3. [Adapting to New Subjects](#adapting-to-new-subjects)
4. [Source Management](#source-management)
5. [Improvement Workflow](#improvement-workflow)
6. [Version Control Strategy](#version-control-strategy)
7. [Best Practices](#best-practices)
8. [Future Extensions](#future-extensions)

---

## How This System Works

### Core Principle: Error-Driven Learning

The system is built on a simple but powerful idea:

**Learning happens through guided discovery, not immediate solutions.**

When a learner makes an error:
1. AI identifies the error by **line number** and **error type** only
2. Learner corrects their own work based on these hints
3. Only after error-free submission (or explicit request) does the AI provide full explanations

This forces learners to:
- Think through problems themselves
- Develop problem-solving strategies
- Build deeper understanding through iteration

### The Two-Concept Rule

**Maximum 2 new concepts per lesson.**

This prevents cognitive overload and ensures mastery before moving forward. If a lesson requires more than 2 new concepts, it's automatically split into sub-lessons (L01.1, L01.2, etc.).

### Goal-Based Structure

Instead of linear progression, learners choose **goals** (G##) that interest them:

- **G01**: Build a calculator
- **G02**: Create a menu system  
- **G03**: Develop a text game

Each goal lists required commands/concepts and tracks progress.

### Three Lesson Types

**L## (Learning Lessons)**: Introduce max 2 new concepts
- Explain concept at the start
- Provide mini-example (not solution)
- Assign practice task
- Error correction phase

**W## (Review Lessons)**: Combine known concepts (no new concepts)
- Inserted when errors repeat
- Deepen understanding through combination

**T## (Test Lessons)**: Assess mastery of all concepts in a goal
- Only available when all commands in goal are mastered
- Passing = goal completed

---

## How We Developed It

### Iterative Development Process

This system wasn't built in one go. It evolved through iterative refinement:

**Version 1-5**: Basic structure and study mode rules
- Established error-driven learning
- Defined feedback format (line number + error type)
- Created lesson structure

**Version 6-10**: Error classification system
- Added error types (Syntax, Structure, Logic, Input)
- Introduced error levels (0-2)
- Implemented repeat-error triggers

**Version 11-15**: Goal-based flexibility
- Replaced linear progression with goal selection
- Added lesson types (L, W, T)
- Created command tracking system

**Version 16+**: Motivation and reflection
- Added celebration system
- Implemented metacognitive reflection
- Integrated session structure

### Key Development Principle

**Every rule exists because of a real problem.**

We didn't design the system theoretically. Each rule emerged from actual learning sessions:

- "Menu appears twice" error → Structure error category created
- Learner confused by too many new concepts → Two-concept limit established
- Same error repeated 3 times → Automatic review lesson triggered

### Documentation-Driven Development

**Critical practice**: Document EVERYTHING immediately.

When we made a change:
1. Update `readme-config.json` with the new rule
2. Update `error-plan.md` if error-related
3. Add example to relevant template
4. Test the change in next session
5. Refine based on results

This created a feedback loop:
```
Real session → Identify issue → Document solution → Test → Refine → Document refinement
```

---

## Adapting to New Subjects

### Step 1: Identify Your Domain's "Commands"

In programming, "commands" are clear: `while`, `if`, `print`, etc.

For other subjects, identify the **smallest learnable units**:

**Language Learning (Esperanto, Spanish, etc.)**
- Verb conjugations: "present tense -as", "past tense -is"
- Grammar structures: "accusative case", "adjective agreement"
- Vocabulary sets: "food words", "travel phrases"

**Mathematics**
- Formulas: "quadratic formula", "derivative rules"
- Proof techniques: "contradiction", "induction"
- Calculation methods: "long division", "completing the square"

**Music Theory**
- Concepts: "major scale", "chord progressions"
- Notation: "treble clef reading", "rhythm notation"
- Techniques: "interval recognition", "chord voicing"

**History**
- Analytical skills: "source evaluation", "causation analysis"
- Frameworks: "political context", "economic factors"
- Methods: "timeline construction", "comparative analysis"

### Step 2: Define Goals

Each goal represents a concrete, achievable project or milestone.

**Examples:**

**Esperanto**
- G01: "Introduce yourself and describe your daily routine"
- G02: "Order food in a restaurant and ask for directions"
- G03: "Write a short letter about your weekend"

**Mathematics**
- G01: "Solve quadratic equations using all three methods"
- G02: "Calculate derivatives of polynomial functions"
- G03: "Prove basic properties of even and odd functions"

**Music Theory**
- G01: "Identify and construct major and minor scales"
- G02: "Analyze chord progressions in popular songs"
- G03: "Write a simple four-bar melody with harmony"

### Step 3: Break Down Each Goal

For each goal, list **all** required "commands" (skills/concepts):

```json
{
  "id": "G01",
  "title": "Introduce yourself in Esperanto",
  "commands": {
    "present_tense_as": false,
    "personal_pronouns": false,
    "accusative_n": false,
    "basic_adjectives": false,
    "word_order": false
  }
}
```

### Step 4: Create Lesson Sequence

Design lessons that introduce **maximum 2 new concepts** each:

**L01**: Present tense (-as) + Personal pronouns
- Learn: mi/vi/li/ŝi/ĝi + verb conjugation
- Practice: Simple sentences "Mi estas", "Vi laboras"

**L02**: Accusative case (-n) + Word order
- Learn: Direct object marking + flexible word order
- Practice: "Mi vidas la hundon" vs "La hundon mi vidas"

**W01**: Review - Combining tenses and cases
- No new concepts
- Practice: Complex sentences with multiple elements

**T01**: Test all concepts from G01
- Only when all commands are `true`
- Comprehensive assessment

### Step 5: Adapt Error Classification

Redefine error types for your domain:

**Language Learning**
- **Syntax**: Wrong conjugation, missing affixes
- **Structure**: Word order errors, missing required elements
- **Logic**: Correct grammar but wrong meaning/context
- **Input**: Vocabulary not yet learned, incorrect case marking

**Mathematics**
- **Syntax**: Notation errors, sign mistakes
- **Structure**: Steps in wrong order, skipped necessary steps
- **Logic**: Correct calculation but wrong method/approach
- **Input**: Using formulas not yet learned, incorrect substitution

### Step 6: Create Subject-Specific Cheat Sheet

Your `cheat-sheet.md` should mirror programming's reference format:

**Esperanto Example:**
```markdown
# Verb Conjugations

Present tense: verb root + -as
- mi laboras (I work)
- vi studas (you study)

Past tense: verb root + -is
- mi laboris (I worked)

# Grammar Structures

Accusative case: noun + -n (for direct objects)
- Mi vidas la hundon. (I see the dog.)
```

**Mathematics Example:**
```markdown
# Basic Derivatives

Power rule: d/dx(x^n) = nx^(n-1)

Product rule: d/dx(uv) = u'v + uv'

Chain rule: d/dx(f(g(x))) = f'(g(x)) · g'(x)

# Common Errors

❌ Forgetting to multiply by inner derivative in chain rule
✓ Always identify outer and inner function first
```

---

## Source Management

### The One-Source Principle

**Critical rule**: The AI should ONLY use information from explicitly provided sources.

This ensures:
- Consistency across all learning sessions
- No "hallucinated" information
- Clear boundaries of what learner has been taught
- Reproducible learning path

### Source Files

The system uses these files as its ONLY sources of truth:

**1. readme-config.json**
- All system rules and behaviors
- Feedback formats
- Error classification
- Session structure

**2. teaching-plan.json**
- All goals, lessons, tests
- Command/skill definitions
- Prerequisites and dependencies

**3. cheat-sheet.md**
- Commands/concepts already learned
- Examples and syntax
- Common error patterns

**4. error-plan.md**
- Error type definitions
- Error level meanings
- Trigger rules

**5. Current session files** (during active learning)
- learning-log.json: Past sessions and reflections
- progress.json: Current mastery status
- error-history.json: Error patterns and trends

### External Research (Future)

When information is needed but not in primary sources:

1. AI recognizes gap
2. Conducts research with **minimum 2 independent sources**
3. Presents findings WITH citations
4. Asks: "Should I add this to the knowledge base?"
5. Only with consent → adds to knowledge file with sources

**Template for knowledge entries:**
```json
{
  "topic_id": "X99",
  "title": "New Concept Name",
  "items": [
    {
      "name": "Specific term or skill",
      "definition": "Evidence-based definition",
      "sources": [
        {
          "author": "Smith, J.",
          "year": 2024,
          "title": "Title of Source",
          "url": "https://...",
          "type": "journal"
        },
        {
          "author": "Jones, A.",
          "year": 2023,
          "title": "Another Source",
          "url": "https://...",
          "type": "book"
        }
      ]
    }
  ]
}
```

### Source Validation Checklist

Before each AI response:
- [ ] Is this information in readme-config.json?
- [ ] Is this command in teaching-plan.json?
- [ ] Is this concept in cheat-sheet.md?
- [ ] Is this error type in error-plan.md?
- [ ] If none of above → DO NOT USE or trigger research

---

## Improvement Workflow

### How We Iterated on This System

**Real session → Documentation → Refinement loop**

#### Example Iteration 1: Menu Error

**Problem observed**: Learner's menu appeared twice in output

**Documentation**:
1. Added "Structure Errors" category to error-plan.md
2. Created specific entry: "Menu outside AND inside loop"
3. Updated teaching-plan.json with prerequisite check

**Refinement**:
- Next session tested detection
- Refined error message wording
- Added to cheat-sheet.md under "Common Errors"

#### Example Iteration 2: Too Many Concepts

**Problem observed**: Learner struggled with lesson introducing 4 new concepts

**Documentation**:
1. Added "two-concept rule" to readme-config.json
2. Created auto-split mechanism for overloaded lessons
3. Updated teaching-plan.json with sub-lesson format (L##.1, L##.2)

**Refinement**:
- Tested auto-split in next complex lesson
- Refined split logic (when exactly to split)
- Added sub-lesson examples to documentation

#### Example Iteration 3: Repeated Errors

**Problem observed**: Same error appeared 3 times without improvement

**Documentation**:
1. Added error levels (0-2) to error-plan.md
2. Created trigger rule: "3+ repetitions → automatic W## review"
3. Updated error-history.json format to track repetitions

**Refinement**:
- Tested trigger in next session with repeated error
- Refined: when to downgrade from level 2 to level 1
- Added success criteria for error mastery

### Your Improvement Workflow

**For each learning session:**

1. **Conduct session** using current system
2. **Document what happened**:
   - What worked well?
   - What caused confusion?
   - What errors occurred?
   - What felt missing?

3. **Identify patterns** (after 3-5 sessions):
   - Same problem recurring?
   - Same question asked multiple times?
   - Unexpected behavior?

4. **Propose solution**:
   - New rule?
   - Refined error category?
   - Additional lesson type?
   - Changed feedback format?

5. **Document in appropriate file**:
   - System behavior → readme-config.json
   - Error patterns → error-plan.md
   - New concepts → teaching-plan.json + cheat-sheet.md

6. **Test in next session**:
   - Does it solve the problem?
   - Does it create new problems?
   - Is it clear to follow?

7. **Refine and document refinement**:
   - Update files with refined version
   - Add "version note" explaining change
   - Keep old version documented for reference

### Version Notes Format

When making significant changes, add version notes:

```json
{
  "version": "17",
  "date": "2025-11-30",
  "changes": [
    "Added automatic sub-lesson splitting for lessons with >2 new concepts",
    "Refined error level triggers: now requires 3 repetitions instead of 2",
    "Added celebration system for milestone achievements"
  ],
  "rationale": [
    "Learners struggled with cognitive load in complex lessons",
    "Error level 2 was triggered too early, causing unnecessary reviews",
    "Positive reinforcement was missing from the system"
  ],
  "testing_results": "Tested over 5 sessions, all improvements validated"
}
```

---

## Version Control Strategy

### File Naming Convention

Use version numbers for major iterations:

- `readme-config-v1.json` → `readme-config-v2.json` → etc.
- `teaching-plan-v1.json` → `teaching-plan-v2.json` → etc.

**When to increment version:**
- Major structural change
- New core principle added
- Significant rule modification

**Keep all versions** in archive folder for reference.

### Git Strategy (Recommended)

```
main branch: Current stable version
dev branch: Testing new features
archive/ folder: All previous versions

Commit messages:
- "feat: Add automatic lesson splitting"
- "fix: Correct error level trigger threshold"
- "docs: Update error-plan with new category"
- "refine: Improve celebration message format"
```

### What to Version

**Always version:**
- readme-config.json
- teaching-plan.json
- error-plan.md
- cheat-sheet.md

**Never version (personal data):**
- learning-log.json (your personal sessions)
- progress.json (your personal progress)
- error-history.json (your personal errors)

**Do provide templates:**
- learning-log-template.json (anonymized structure)
- progress-template.json (anonymized structure)
- error-history-template.json (anonymized structure)

---

## Best Practices

### For Learners

**1. Start small**
- Choose simple first goal
- Don't rush through lessons
- Reflect after each session

**2. Trust the process**
- Error-driven learning feels frustrating initially
- Correcting your own errors builds deeper understanding
- Resist urge to ask for immediate solutions

**3. Document your journey**
- Keep learning log updated
- Note what strategies work for you
- Track your error patterns

**4. Celebrate progress**
- Acknowledge small wins
- Track your streak
- Review how far you've come

### For System Designers

**1. Real problems only**
- Don't add features speculatively
- Wait for pattern to emerge (3+ occurrences)
- Design from actual learner needs

**2. Test before documenting**
- Try the change in real session
- See if it actually helps
- Refine based on real feedback

**3. Keep two-concept limit sacred**
- This is the core of cognitive load management
- If lesson needs more → split it
- No exceptions

**4. Sources are boundaries**
- AI can only use what's documented
- This is a feature, not a bug
- Keeps learning path consistent

**5. Document immediately**
- Don't rely on memory
- Write down change rationale
- Future you will thank present you

### For Subject Adapters

**1. Define "commands" clearly**
- Must be testable (can you check if learner has mastered it?)
- Must be composable (can combine with others)
- Must be atomic (can't be broken down further without losing meaning)

**2. Start with one goal**
- Build complete lesson sequence for ONE goal
- Test thoroughly
- Then add more goals

**3. Error types must fit domain**
- Don't force programming error categories
- Create error types that make sense for your subject
- Test: Can learner understand the error type label?

**4. Cheat sheet is critical**
- This is learner's constant reference
- Keep format consistent
- Update after EVERY lesson

---

## Future Extensions

### Planned Features

**1. Knowledge Base System**
- Structured storage of domain knowledge
- Source tracking for all information
- Automatic research for gaps
- Evidence-based learning content

**2. Multiple Learning Paths**
- Foundation-oriented path (theory first)
- Application-oriented path (practice first)
- Adaptive path switching based on learner style

**3. Spaced Repetition Integration**
- Track concept mastery over time
- Schedule review sessions automatically
- Prevent knowledge decay

**4. Collaborative Learning**
- Share anonymized teaching plans
- Community-contributed goals
- Peer review of lesson sequences

**5. AI Tutor Training**
- Fine-tune AI on successful teaching patterns
- Personalize feedback style
- Adapt to learner's communication preferences

### How to Extend

**To add a new feature:**

1. **Document the need**
   - What problem does it solve?
   - How often does this problem occur?
   - What's the impact if not solved?

2. **Design minimally**
   - What's the simplest version that solves the problem?
   - Can it integrate with existing structure?
   - Does it violate core principles?

3. **Add to appropriate file**
   - System behavior → readme-config.json
   - New data structure → create new template file
   - New process → update relevant .md file

4. **Test thoroughly**
   - Use in real sessions
   - Get feedback from multiple learners
   - Refine based on actual usage

5. **Document the extension**
   - Update this guide
   - Add examples
   - Explain integration points

---

## Making This Universal

### Vision: One System, All Subjects

The goal is to create a system that works for ANY subject with minimal adaptation.

**What stays the same:**
- Study mode (error-driven, no immediate solutions)
- Two-concept limit per lesson
- Goal-based structure
- Lesson types (L, W, T)
- Error tracking and levels
- Session structure and reflection

**What adapts per subject:**
- Definition of "commands" (skills/concepts)
- Error type categories
- Example content in lessons
- Cheat sheet format
- Assessment criteria

### Cross-Domain Learning

Once you have multiple subjects implemented:

**Shared progress dashboard**
- Track progress across all subjects
- Identify learning patterns that work across domains
- Apply successful strategies from one subject to another

**Universal principles emerge**
- How you learn best (visual? practice-heavy? theory-first?)
- Your error patterns (rush through? overthink? miss details?)
- Optimal session length and frequency

**Transfer strategies**
- "I learned X by doing Y in Subject A, can I apply Y to Subject B?"
- Cross-domain analogies
- Meta-learning skills

---

## Getting Started

### For Your First Subject Adaptation

**Week 1: Planning**
1. Define 3-5 goals for your subject
2. List all "commands" (skills/concepts) needed
3. Map which commands are needed for each goal

**Week 2: Build First Goal**
1. Create lesson sequence for Goal 1
2. Write learning lesson (L01) for first 2 concepts
3. Test it yourself or with a learner

**Week 3: Iterate**
1. Document what worked and what didn't
2. Refine lesson content
3. Create L02 for next 2 concepts

**Week 4: Complete First Goal**
1. Finish all lessons for Goal 1
2. Create review lesson (W01)
3. Create test (T01)
4. Validate complete sequence

**Week 5: Expand**
1. Build Goal 2 using lessons learned
2. Start Goal 3
3. Document patterns that emerge

**Week 6: Systematize**
1. Create your subject's cheat-sheet.md
2. Define your subject's error categories
3. Write subject-specific adaptation guide

### Success Criteria

You know your adaptation works when:

- [ ] Learner can progress without external help
- [ ] Error feedback is clear and actionable
- [ ] Two-concept limit feels natural for the subject
- [ ] Lessons build logically on each other
- [ ] Tests accurately assess mastery
- [ ] Cheat sheet serves as complete reference
- [ ] System can be handed to another learner and work immediately

---

## Questions to Ask Yourself

### When Designing a Lesson

- Can I explain the new concept in 2-3 sentences?
- Can I provide a mini-example that doesn't solve the practice task?
- Is the practice task achievable with ONLY known concepts + the 2 new ones?
- What are the 3 most likely errors learners will make?
- How can I give feedback without giving away the solution?

### When Classifying an Error

- Which of the 4 types (Syntax/Structure/Logic/Input) fits best?
- Can the learner understand what "Structure error" means in this context?
- Is this error likely to repeat?
- What would help the learner avoid this error in the future?

### When Defining a Goal

- Can this be achieved in 5-10 lessons?
- Can I clearly list ALL required skills/concepts?
- Is there a concrete, testable outcome?
- Will completing this goal feel like an achievement?
- Does this goal motivate the learner?

### When Creating Source Material

- Is this information from a reliable source?
- Can I cite where this came from?
- Is this the simplest, clearest explanation available?
- Would another expert in this field agree with this?
- Have I documented the source properly?

---

## Contributing Back

If you create an adaptation for a new subject, consider sharing:

**Minimal share:**
- Your teaching-plan-template.json (anonymized)
- Your subject-specific error-plan.md
- Your cheat-sheet template

**Full share:**
- Complete adaptation guide
- Lessons learned and refinements
- Common pitfalls to avoid
- Success metrics

**How to share:**
- Create public repository
- Use same file structure
- Include adaptation guide
- Link back to original system

This creates a library of adaptations that helps everyone.

---

## Final Thoughts

This system exists because of:

1. **Real learner struggles** → Rules that address actual problems
2. **Iterative refinement** → Continuous improvement based on feedback
3. **Strict documentation** → Everything written down immediately
4. **Source discipline** → Only using verified information
5. **Core principles** → Two-concept limit, error-driven, goal-based

When adapting to your subject:
- Honor these principles
- Document your process
- Test with real learners
- Share what you learn

Together, we can build a universal learning system that works for anyone, learning anything.

---

**Version 1.0 – November 2025**

*This guide will evolve as the system evolves. Document your improvements and share them forward.*
