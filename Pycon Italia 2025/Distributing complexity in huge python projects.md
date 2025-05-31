# Distributing complexity in huge python projects.

https://2025.pycon.it/en/event/distributing-complexity-in-huge-python-projects

Speaker: [Maxim Danilov](https://www.linkedin.com/in/danilovmy/)

---

Complexity

- Structural: can be removed by changing the coding paradigm 
- Cognitive 
- Accidental

- Technical (essential complexity): can be frozen, reduced but can't be removed.

Complexity grows with project:

- complex business tasks
- frequency of changes
- missing knowledge

These 3 complexity grow and they mix, creating point of high complexity

---

Simplicity should be set as KPI

https://github.com/danilovmy/dependency-extractor

His tool to measure following metrics

---

CCL index: count of code lines

Measure of project size

Kind of broken by formatters like Ruff
Verbose != complex, longer code can be clearer

---

Class / Function index

OOP vs Functional programming

Broken by functions compositions

---

Dependency index

Coupling / Cohesion index

---

Another tool

https://pypi.org/project/radon/

---

Should always compute metrics before and after refactoring

---

## Refactoring

Zero tech debt zone (files which are changed a lot)

Refactoring is not always a solution

## Increase abstraction level

Article by Sandi Metz

OO with right abstraction is more constly than a simple function but is much less costly than a complex function