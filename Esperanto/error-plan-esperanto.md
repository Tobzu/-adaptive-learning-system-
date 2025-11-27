# Error Plan – Esperanto

## Error Types for Esperanto Language Learning

### Morphology Errors
**Definition:** Incorrect word forms, wrong conjugation endings, missing case markers

**Examples:**
- ❌ `Mi laboras` instead of `Mi laboras` (wrong ending)
- ❌ `Mi vidas hundon` written as `Mi vidas hundo` (missing -n accusative)
- ❌ `Vi studi` instead of `Vi studas` (wrong present tense ending)
- ❌ `Ŝo laboras` instead of `Ŝi laboras` (wrong pronoun form)

**Common pattern:** Present tense -as ending, -n accusative, adjective-noun agreement

---

### Structure Errors
**Definition:** Word order problems, missing required case markers, incorrect sentence construction

**Examples:**
- ❌ `Manĝas pomon mi` (wrong word order – should be verb later or with object marked)
- ❌ `Mi vidas la pomo` (missing -n on direct object)
- ❌ `Laboris mi multajn horojn` (awkward structure – requires special context)
- ❌ `La granda malgranda libro` (contradictory adjectives, logical structure error)

**Common pattern:** Word order flexibility in Esperanto, but accusative MUST mark direct objects

---

### Semantic Errors
**Definition:** Grammatically correct but semantically wrong, incorrect nuance, wrong word choice

**Examples:**
- ❌ `Mi manĝas la ĉambron` (eating a room – grammatically correct, semantically nonsensical)
- ❌ `La suno dormas` (grammatically possible, but semantically odd – sun doesn't sleep)
- ❌ Using `ŝi` (she) for a masculine noun
- ❌ Confusing similar words: `lerni` (learn) vs. `studi` (study) in wrong context

**Common pattern:** Real-world meaning, logical consistency

---

### Vocabulary Errors
**Definition:** Using words not yet taught, incorrect word forms, undefined words

**Examples:**
- ❌ Using a word from L03 in L01 (too advanced)
- ❌ Inventing word forms: `laboristo` (worker) before learning noun suffixes
- ❌ `Mi vidas la kato` (if "kato" not yet introduced in dictionary.txt)

**Common pattern:** Words, prefixes, suffixes outside current lesson scope

---

## Error Levels

### Level 0: Learner Self-Corrects Immediately
- Error spotted and fixed in same attempt
- Understanding appears solid
- No follow-up needed

### Level 1: Error Corrected with Hints
- Learner needed line number + error type feedback
- Corrected on second or third attempt
- Partial understanding present

### Level 2: Persistent Error (3+ Occurrences)
- **Trigger:** Same error type appears 3+ times across sessions
- **Action:** Automatic review lesson (W##) inserted
- **Focus:** Drill and reinforce the specific rule

---

## Trigger Rules

### Auto-Insert Review Lesson
- **Condition:** Error level reaches 2 (same error 3+ times)
- **Action:** Insert W## lesson before next L## lesson
- **Duration:** 1-2 sessions focusing on the problematic pattern

### Progress to Test
- **Condition:** All commands in goal marked `true` (mastered)
- **Action:** Unlock T## test lesson
- **Requirement:** Must pass T## with 100% accuracy or rerun specific L## lesson

### Move to Next Goal
- **Condition:** Goal test passed
- **Action:** Mark goal as completed, move to next G##
- **Celebration:** Level 2 achievement message

---

## Sources for Error Classification

All error feedback comes ONLY from:
- `grammar.txt` – Official Esperanto grammar rules
- `dictionary.txt` – Authorized word list and forms
- `teaching-plan-esperanto.json` – Lesson scope and concepts

**No errors classified outside these boundaries.**
