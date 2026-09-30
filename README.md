Skills I use daily for code work.

Largely inspired by the work of [Matt Pocock](https://github.com/mattpocock)

## Usage

Each skill lives in its own folder as a `SKILL.md` with a `name` and `description` frontmatter. Drop the folder in `~/.config/crush/skills/` and it's picked up automatically. Invoke a skill by asking for it by name (e.g. "kr-review this branch"); skills with `disable-model-invocation: true` only run when you name them explicitly.


## Planning & thinking

- **[grill-me](./grill-me/SKILL.md)**: Interview you relentlessly about a plan, decision, or idea, working a design tree in rounds to surface every hidden assumption until you reach shared understanding.
- **[grill-with-docs](./grill-with-docs/SKILL.md)**: Grilling session that also builds your project's domain model, sharpening terminology and updating `GLOSSARY.md` and ADRs inline.
- **[to-questionnaire](./to-questionnaire/SKILL.md)**: Turn a decision you can't answer alone into a Markdown questionnaire aimed at the gap between what a recipient knows and what you need back.
- **[research](./research/SKILL.md)**: Investigate a question against high-trust primary sources and capture the findings as a cited Markdown file in the repo, run as a background agent.

## Design & modelling

- **[domain-modeling](./domain-modeling/SKILL.md)**: Actively build and sharpen a project's domain model by challenging terms, stress-testing with scenarios, and updating `GLOSSARY.md` and ADRs inline.
- **[codebase-design](./codebase-design/SKILL.md)**: Shared discipline and vocabulary for designing deep modules: small interfaces, clean seams, testable through the interface.
- **[improve-codebase-architecture](./improve-codebase-architecture/SKILL.md)**: Scan a codebase for deepening opportunities, present them as a visual HTML report, then grill through whichever one you pick.
- **[prototype](./prototype/SKILL.md)**: Build a throwaway prototype to answer a design question: a single shareable HTML file for state/logic, or several toggleable UI variations.

## Building

- **[implement](./implement/SKILL.md)**: Build the work described by a spec or set of tickets, driving `/tdd` at pre-agreed seams and closing out with `/code-review` before committing.
- **[tdd](./tdd/SKILL.md)**: Test-driven development with a red-green-refactor loop. Builds features or fixes bugs one vertical slice at a time.

## Review & ship

- **[kr-review](./kr-review/SKILL.md)**: Review all changes on the current branch versus `master` against the KR merge-request checklist (general, backend, tooling), run `nr-check all`, report every issue, and fix any found.
- **[code-review](./code-review/SKILL.md)**: Two-axis review of the diff since a fixed point: **Standards** (does it follow the repo's coding standards, plus a Fowler smell baseline?) and **Spec** (does it faithfully implement the originating issue/spec?), run as parallel sub-agents.
- **[pr](./pr/SKILL.md)**: The shape a pull request body should take: a summary as the smallest visual that makes the change clear, before/after evidence that it works, and a merge-danger call (one-way or two-way door, plus blast radius).

## Workflow & communication

- **[handoff](./handoff/SKILL.md)**: Compact the current conversation into a handoff document (saved to the OS temp dir) so a fresh agent can pick up the work, including suggested next skills.
- **[retro](./retro/SKILL.md)**: Suggest improvements to the coding agent's environment (navigation, automated checks, coding standards, steering files, tooling) after a session, most severe first.
- **[wait-what](./wait-what/SKILL.md)**: Re-pitch a message that didn't land, in ASD-STE100 Simplified Technical English and the repo's ubiquitous language from `GLOSSARY.md`.
- **[teach](./teach/SKILL.md)**: Teach you a new skill or concept across sessions, building beautiful mission-grounded HTML lessons, reference docs, and learning records in a stateful teaching workspace.

## Infrastructure & ops

- **[wizard](./wizard/SKILL.md)**: Generate an interactive bash wizard that walks a human through steps only they can perform: provisioning infrastructure, setting up credentials or CI secrets, walking an unfamiliar third-party dashboard, or running a one-off migration or cutover.
