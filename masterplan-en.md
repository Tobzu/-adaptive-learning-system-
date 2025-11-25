# Master Plan – Universal Learning System (Version 2)

This master plan extends Version 1 with a new core function: **external research by the AI** when information is not available in the primary sources.

---

## 1. New Principle: External Research for Knowledge Gaps

When **information is needed during a learning session that is not in the existing knowledge base**, the AI should do the following:

1. **Recognize** that the information is missing
2. **Conduct online research** (with source citations, publication date, origin)
3. **Inform the user** that new information has been found
4. **Ask back** whether this information should be adopted into the knowledge base
5. Only with consent → **Integrate into the knowledge file**

### Rules for External Research

- The AI researches **only** when content is clearly not in the primary sources
- Each research must contain **at least two independent sources**
- The AI must **not save anything automatically**
- Storage occurs **only after asking back** and consent
- New entries must use the same structure as the existing `knowledge_*.json`

---

## 2. Integration into the Existing System Architecture

External research complements the existing building blocks of the learning system:

### 2.1 Curriculum (`teaching_plan_*.json`)

- Learning units can require loading certain knowledge elements as prerequisites
- If a topic does not exist in the knowledge base → automatic research
- Curriculum remains adaptive and error-driven

### 2.2 Knowledge Base (`knowledge_*.json`)

Extensions follow this schema:

```json
{
  "topic_id": "X99",
  "title": "Title of new knowledge",
  "items": [
    {
      "name": "Term or object",
      "definition": "Evidence-based definition",
      "sources": [
        {"author": "...", "year": 2024, "title": "...", "url": "..."},
        {"author": "...", "year": 2023, "title": "...", "url": "..."}
      ]
    }
  ]
}
```

### 2.3 Study Mode

- With knowledge gaps: Notice "Not in primary sources – research needed"
- Research results are clearly separated from learning content
- No storage without consent

### 2.4 Error Plan / Error History

- Error category "knowledge gap" is added
- If user repeatedly asks about a missing topic → system suggests storage

---

## 3. New Error Category: Knowledge Gap

```
Category: knowledge_gap
Description: User asks question about content that is not in any primary source
Trigger: AI finds no matching entries in knowledge file
Response: Online research + ask back + optional storage
```

Levels:
- **Level 1**: One-time knowledge gap (normal)
- **Level 2**: Repeated knowledge gap → system recommends structural expansion of knowledge base

---

## 4. Process Flow for Knowledge Gap

### Step 1 – Recognition
The AI analyzes all available files (`knowledge`, `teaching_plan`, `cheat-sheet`, etc.)

### Step 2 – Research
- At least two independent sources
- Prefer scientific/reputable sources
- Complete citation

### Step 3 – Ask Back
```
Should this new knowledge be added to the knowledge base?
```

### Step 4 – Integration
- Only with explicit consent
- Entry follows knowledge template
- Version increment (`knowledge_vX.json → knowledge_vX+1.json`)

---

## 5. Goal

Through this extension, the learning system becomes:

- **Self-healing** with knowledge gaps
- **Scalable** for all subjects
- **Evidence-based**, as all new information is researched and documented
- **Controlled**, because no automatic storage occurs

This system can now be used for both Python and future subjects (Esperanto, Physics, Psychology, etc.)

---

## 6. Outlook

- Extension with automatic duplicate checking in knowledge files
- Classification of external sources by quality (journal, book, blog, Wikipedia)
- Automated suggestions for new learning modules based on new knowledge entries

---

## 7. Note: Two Dynamic Main Learning Paths per Knowledge Base (Version 2)

For each subject area from Version 2:

As soon as a new `knowledge_*.json` has been uploaded or initially created, the system should suggest **at least two different main paths** for learning the content. These main paths are:

- **Main path A** – e.g., more **foundation-/structure-oriented**
- **Main path B** – e.g., more **application-/project-oriented** or **practice-oriented**

### 7.1 Dynamics Like in the Curriculum

- The main paths are **not statically** defined but are **as dynamic** as the units in `teaching_plan_*.json`
- Both paths should:
  - Use units (L##, W##, T##, modules) **in different order** or weighting
  - React to **error data** and **practice needs** (e.g., detours via additional tests, review blocks)
  - Optionally be **merged** when the learner has completed both perspectives (e.g., foundations + application)

### 7.2 Status: Note, Detailed Design Later

- The exact structure of these main paths (e.g., names, IDs, JSON schema) will be **defined only at the end of the project**
- Current purpose of this section:
  - Ensure that the system long-term provides **at least two main learning paths per subject**
  - Record that these paths are **coupled to the curriculum logic** and should be **adaptive**
- Later, `teaching_plan_TEMPLATE.json` could provide a structure like:
  - `"paths": ["foundation_path", "application_path"]`
  - Including triggers that allow switching or detours based on errors

---

## 8. Implementation Priority

**Current priority (for initial release):**
1. Core system (study mode, error tracking, goals)
2. Basic file structure
3. Template documentation

**Future enhancements (post-release):**
1. External research mechanism
2. Knowledge base expansion
3. Multiple learning paths
4. Automatic source quality classification

---

**Version 2.0 – November 2025**
