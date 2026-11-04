This is the current content of your clean-code-principles skill, ready to copy into SKILL.md. The MIT license applies to the skill text you publish; it doesn’t relicense Robert C. Martin’s book. Keep the attribution, and make sure the license matches what you intend to release.


name: clean-code-principles
category: software-development
description: Clean Code principles from Robert C. Martin book.
version: 1.0.0
author: Sajjad
license: MIT
metadata:
  hermes:
    tags: [clean-code, refactoring, naming, functions, testing, oop]
    related_skills: [pyscaffold-project-structure]


Clean Code Principles (Robert C. Martin)

When to Use
- Writing new code — apply naming, function, and class principles
- Code review — check against these standards
- Refactoring legacy code — identify smells (large functions, bad names, commented code, null returns)
- Teaching/mentoring — shared vocabulary for code quality

Clean Code Principles (Robert C. Martin)

Use when writing, reviewing, or refactoring code. Applies to all languages.

Core Principles

1. Meaningful Names
- Intention-revealing: elapsedTimeInDays not d
- Avoid disinformation: accountList only if it's actually a List
- Make meaningful distinctions: Product vs ProductInfo vs ProductData
- Pronounceable: genymdhms → generationTimestamp
- Searchable: single-letter names only for local loop counters
- No encodings: no Hungarian notation, no member prefixes (m_)
- Classes: nouns (Customer, WikiPage)
- Methods: verbs (postPayment, deletePage)
- One word per concept: fetch/retrieve/get → pick one

2. Functions
- Small! First rule. Second rule: smaller than that.
- Do one thing: If you can extract another function with a different name, it does >1 thing
- One level of abstraction per function
- Stepdown rule: read top-to-bottom, each function calls next level down
- Function arguments: ideal=0 (niladic), 1 (monadic), 2 (dyadic), avoid 3+ (triads)
- No flag arguments: split into two functions
- Argument objects for 3+ related params
- Prefer exceptions to return codes
- Extract try/catch blocks into their own functions
- Error handling is one thing
- Don't repeat yourself (DRY)

3. Comments
- Comments don't make up for bad code — refactor instead
- Explain yourself in code: if (employee.isEligibleForFullBenefits()) > if ((employee.flags & HOURLY_FLAG) && (employee.age > 65))
- Good comments: legal, informative, intent, clarification, warning, TODO, amplification
- Bad comments: mumbling, redundant, misleading, mandated, journal, noise, scary noise
- Don't use comment when function/variable works
- No commented-out code — delete it, git has history

4. Formatting
- Vertical formatting: newspaper metaphor — summary at top, details below
- Vertical openness between concepts, density for related lines
- Horizontal: line length ~120 chars, alignment only when it helps
- Indentation: consistent, no dummy scopes
- Team rules over personal preferences

5. Objects & Data Structures
- Data abstraction: hide implementation, expose abstract interfaces
- Data/Object anti-symmetry: objects hide data behind methods; data structures expose data
- Law of Demeter: only talk to immediate friends (a.b().c() is a train wreck)
- Hybrids (half object, half data structure) are worst of both

6. Error Handling
- Use exceptions not return codes
- Write try-catch-finally first
- Use unchecked exceptions (don't force catch everywhere)
- Provide context with exceptions
- Define exception classes by caller's needs
- Define normal flow — special case pattern for null
- Don't return null — throw or return special case
- Don't pass null

7. Boundaries
- Third-party code: wrap it, don't let it leak through
- Learning tests > free exploration
- Clean boundaries: adapters, facades

8. Unit Tests (F.I.R.S.T.)
- Fast — run often
- Independent — no order dependency
- Repeatable — any environment
- Self-validating — boolean pass/fail
- Timely — written before production code (TDD)
- Three laws of TDD: fail first, minimal code, minimal test
- Clean tests: readable, domain-specific language, one assert per test
- Single concept per test

9. Classes
- Small! First rule. Second: smaller.
- Single Responsibility Principle (SRP): one reason to change
- Cohesion: methods use instance variables
- Many small classes > few large ones
- Organize for change: isolate from change

10. Systems
- Separate construction from use (factories, DI)
- AOP for cross-cutting concerns
- Iterative refinement — start simple, add complexity when needed

The Boy Scout Rule
Leave the campground cleaner than you found it.

Prequel
- Conway's Law: org structure → system structure
- Principles > practices
- Professionalism = writing clean code
