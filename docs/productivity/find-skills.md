Quickstart:

```bash
npx skills add mattpocock/skills --skill=find-skills
```

```bash
npx skills update find-skills
```

[Source](https://github.com/mattpocock/skills/tree/main/skills/productivity/find-skills)

## What it does

`find-skills` discovers and evaluates installable agent skills for a concrete task. Its defining constraint is **discovery first**: it searches the skill ecosystem and inspects real candidates before recommending one, rather than guessing from a skill name or stopping at the first match.

The workflow is capability-aware. It can use the Skills CLI when shell access exists, or web and GitHub discovery in environments where the CLI is unavailable.

## When to reach for it

Type `/find-skills`, or the agent reaches for it automatically when you ask to find, compare, or install a skill, or when a specialized reusable capability is likely to exist in the open skill ecosystem.

Use it for skill discovery rather than general research. For primary-source engineering research that should leave a cited artifact in the repo, use [research](https://aihero.dev/skills-research).

## Discovery first

The skill turns the actual job into specific search terms, searches more than one plausible wording when needed, and then vets the candidates. Repository reputation, maintenance, adoption signals, tool requirements, and the contents of the real `SKILL.md` all matter; popularity alone does not decide the recommendation.

The output is intentionally small: the best fit first, only the alternatives that materially differ, and a valid installation path when the current environment supports one.

## It's working if

- The search terms reflect the concrete task rather than a broad category.
- Recommended skills have had their actual source inspected.
- The recommendation explains fit and limitations instead of only reporting popularity.
- A missing skill does not block the underlying task.

## Where it fits

This is a reach-for-it-anytime standalone discovery skill. It complements [ask-matt](https://aihero.dev/skills-ask-matt): `ask-matt` routes among the skills already in this repository, while `find-skills` looks outside the repository for capabilities that may be worth adding.
