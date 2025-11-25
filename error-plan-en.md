# Error Plan – Version 2

This error plan provides a reference for **error detection, classification and documentation**.

---

## 🎯 Purpose of the Error Plan

- Clearly recognize errors
- Correctly classify errors (Level 0–2)
- Consistently document errors
- Automatically classify repeated errors correctly
- Quickly identify error causes
- Support learners in a targeted manner

---

## 🧱 Error Levels

### **Level 0 – Error no longer occurs**
- User has repeatedly solved the error correctly
- At least 2 units without occurrence
- Entry can be archived or ignored

### **Level 1 – Error currently does NOT occur, but was relevant**
- Error was corrected
- User has understood it
- But it can happen again
- Serves as an "observation point"

### **Level 2 – Error currently occurs**
- Frequent or severe error
- Requires targeted exercises or additional tests
- T01.1 or T02.1 can be activated

---

## 🪲 Error Categories

## A) **Structure Errors**
Errors in the basic organization of the code:

- Menu **outside** the loop + **inside** the loop → duplicate menu
- Functions contain logic that doesn't belong there
- Main loop is **inside** a function
- Function call instead of function definition (`menu():` instead of `def menu():`)
- Recursive function call without necessity
- break at the wrong level
- Blocks in wrong order
- Invalid indentation

## B) **Input Errors**
Errors in the area of `input`, `try/except`, boolean values:

- ValueError not caught
- except not under try (syntax error)
- Input is validated but still used
- continue missing → program runs into wrong logic
- else catches EVERYTHING

## C) **Logic Errors**
Errors in case distinction or program structure:

- Option 3 not defined → any number except 1 and 2 ends
- Wrong order of if/elif/else
- No separation of display–input–logic
- Different blocks are mixed
- State is not stored correctly

## D) **Syntax Errors**
Pure Python rule violations:

- Indentation wrong
- except not in right place
- Missing colon
- `==` instead of `=`
- Incomplete function definitions

---

## 📘 Documentation Format (`error_history.json`)

Each entry follows this schema:

```json
{
  "timestamp": "2025-11-25T10:30:00",
  "error_type": "structure",
  "line": 12,
  "level": 2,
  "description": "break at wrong level",
  "lesson": "L03",
  "resolved": false
}
```

**Rules:**
- level 0 → resolved = true
- level 1 or 2 → resolved = false
- level 2 → Additional test (T01.1 or T02.1) possible

---

## 🧪 Typical Errors (as reference)

These errors actually occurred and should be registered:

- Menu appears twice (Level 2)
- `menu():` instead of `def menu():`
- Input validation not in loop
- else catches 4, 5, 99
- Loop in function instead of under function
- try/except in wrong position
- break ends wrong loop
- Input comes before menu
- Menu completely missing
- Functions call themselves

---

## 📌 Extended Rules for Additional Tests (T01.1 / T02.1)

When level = 2 for structure errors or repeated logic errors:

- Execute **T01.1** (mini menu with 2 options)
- Focus: pure structure, order of blocks
- After passing → reduce level to 1

When level = 2 for input/ValueError problems:

- Execute **T02.1** (mini text tool)
- Focus: try/except + continue
- After passing → reduce level to 1

---

## 🔍 Checklist for AI (automatically use in background)

- [ ] Are all `def` at the top?
- [ ] Main loop correctly placed?
- [ ] Menu function without logic?
- [ ] Menu in loop?
- [ ] Input under menu?
- [ ] try/except correctly indented?
- [ ] `continue` present on error?
- [ ] else correctly ordered?
- [ ] Program behavior correctly logically separated?

---

## ✔ Goal

This error plan ensures:

- Consistent error detection
- Clean classification
- Sensible next steps
- Targeted exercises
- Fewer repeated errors
- Clearer learning curve
