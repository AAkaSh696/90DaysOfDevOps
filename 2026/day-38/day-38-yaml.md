## Day 38 – YAML Basics

##  What I Learned

1. YAML is very sensitive to indentation (spaces only, no tabs)
2. Lists can be written in two ways:
   - Dash format:
     - item1
     - item2
   - Inline format:
     [item1, item2]
3. YAML is widely used in DevOps tools like Docker Compose and GitHub Actions

---

##  Task Answers

### Lists in YAML
Two ways:
- Using dashes (-)
- Using inline format [ ]

---

### Multi-line Strings

| (pipe):
- Preserves line breaks
- Used for scripts

> (fold):
- Converts into single line
- Used for long text

---

### YAML Validation

- YAML does not allow tabs
- Only spaces (usually 2 spaces)
- Wrong indentation gives error

Example error:
"mapping values are not allowed here"

---

### Spot the Difference

Correct:
tools:

  - docker
  - kubernetes

Broken:
tools:
- docker
  - kubernetes
    
Issue:
- Indentation is inconsistent
- YAML structure breaks

---
