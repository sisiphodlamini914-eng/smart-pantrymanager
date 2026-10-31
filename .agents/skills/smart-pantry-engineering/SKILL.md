---
name: smart-pantry-engineering
description: Build and validate the Smart Pantry Manager Android app in Java using SQLiteOpenHelper, XML layouts, Activities, Intents, RecyclerView, and testable domain logic. Follow the project assignment rubric in docs/ANTIGRAVITY_BUILD_PROMPT.md, enforce pantry/recipe rules strictly, prefer straightforward maintainable architecture, and validate behavior with Gradle tests and focused Android checks.
---

# Smart Pantry Manager engineering guide

Before making implementation decisions, read `docs/ANTIGRAVITY_BUILD_PROMPT.md` in full and treat it as the authoritative project specification.

## Core project requirements

- Build a native Android app in Java for the Smart Pantry Manager assignment.
- Use XML layouts for the UI and keep Activities focused on navigation and presentation.
- Use SQLite persistence via `SQLiteOpenHelper` and store pantry items and related data reliably across app restarts.
- Use Activities and Intents where navigation is required.
- Use `RecyclerView` for scrolling lists when the UI needs them.
- Keep recipe-matching rules in a testable service or domain class rather than embedding them in an Activity.
- Prefer the simplest architecture that still satisfies the assignment rubric and acceptance criteria.

## Mandatory technology constraints

- Java only for app logic.
- Native Android app, not Kotlin, Jetpack Compose, Room, or web-based substitutes.
- XML-based layouts.
- SQLite with `SQLiteOpenHelper`.
- Android Activities and Intents for navigation when appropriate.
- `RecyclerView` where list display is needed.
- Android-compatible Java testing tools.
- Do not weaken strict pantry/recipe validation to make the app appear more functional.

## Pantry and recipe logic rules

- Implement pantry item creation, viewing, editing, and deletion.
- Validate ingredient names, quantities, units, and required fields before saving.
- Normalize ingredient names consistently.
- Handle units and conversions carefully; never compare incompatible units as if they were equivalent.
- A recipe should only be recommended when every required ingredient is available in sufficient quantity.
- A recipe must be excluded when even one required ingredient is missing or insufficient.
- Keep strict recipe-matching logic testable and transparent.
- Persist data correctly so it survives app restarts.

## Testing and verification expectations

- Add tests for recipe matching covering missing ingredients, insufficient quantities, exact quantities, name normalization, and valid unit conversions.
- Test pantry CRUD operations and persistence.
- Check UI validation, navigation, empty states, and error handling.
- Run Gradle build and relevant tests after meaningful changes.
- Fix failures instead of suppressing them.
- If an emulator, SDK component, or device is unavailable, report the limitation honestly rather than claiming the app was fully validated.

## Native UI and UX standards

- Use a warm kitchen-inspired palette: cream/off-white surfaces, deep forest green primary actions, muted sage accents, charcoal text, and restrained amber warnings.
- Keep a clear hierarchy, readable quantities, accessible controls, and practical touch targets.
- Maintain a polished, usable design across different screen sizes without sacrificing functionality.
- Provide empty, validation, success, and error states where relevant.

## Code quality expectations

- Use meaningful Java class, method, and variable names.
- Keep Activities focused on UI and navigation.
- Separate database logic, domain logic, and presentation concerns.
- Close cursors and resources correctly.
- Handle invalid data and exceptions deliberately.
- Avoid duplication, placeholder implementations, and unnecessary abstractions.
- Add comments only where they explain non-obvious decisions.

## Git and delivery discipline

- Keep commits small and genuinely grouped by feature or fix.
- Do not fabricate build outcomes or screenshots.
- Do not overwrite unrelated user changes.
- Keep the repository and branch structure stable unless a justified change is necessary.
- Never commit secrets, API keys, or machine-specific credentials.

## Recommended workflow

1. Read `docs/ANTIGRAVITY_BUILD_PROMPT.md` and understand the rubric before implementing anything.
2. Design the data model, database helper, domain service, and UI flow around the assignment requirements.
3. Implement core pantry logic and persistence first, then recipe matching and validation.
4. Add unit tests for strict recipe logic and persistence behavior.
5. Run Gradle checks and fix issues before moving on.
6. Keep the implementation maintainable, testable, and aligned with the assignment rubric.

This skill complements the official Android skills. Use the official Android guidance for platform-specific tasks, but rely on this skill for the Smart Pantry Manager project requirements, engineering constraints, and quality bar.
