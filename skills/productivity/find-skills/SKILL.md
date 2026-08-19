---
name: find-skills
description: Discover and evaluate installable agent skills. Use when the user asks to find, search for, compare, or install a skill, or when a specialized capability may be better served by an existing skill from the open ecosystem.
---

# Find Skills

Use **discovery first** when the request is about extending the agent with a reusable capability.

## 1. Resolve the capability

Identify the domain, the concrete job to be done, and the constraints that matter. Turn that into one or more specific search phrases rather than a broad category.

Completion criterion: the search terms describe the actual task closely enough to distinguish useful skills from generic matches.

## 2. Search the skill ecosystem

Use the strongest discovery mechanism available in the current environment:

- With shell access, use `npx skills find <query>` and refine the query when needed.
- Without shell access, search skills.sh and public GitHub sources using the available web or GitHub tools.
- When the user names a source, registry, owner, or repository, scope the search to it first.

Try close alternative terms if the first search is weak. Do not stop at the first plausible result.

Completion criterion: either at least one relevant candidate is found, or the reasonable search variants are exhausted.

## 3. Vet before recommending

Inspect the candidate's real `SKILL.md` and source repository. Prefer maintained, reputable sources and evidence of real use when those signals are available. Check that the skill's trigger, workflow, required tools, and environment assumptions fit the user's task.

Treat popularity as a signal, not proof. A smaller skill can be the better choice when it is materially more specific.

Completion criterion: every recommended candidate has been inspected closely enough to explain why it fits and any important limitation.

## 4. Present the smallest useful set

Recommend the best match first. For each option, give the skill name, source, what it is good for, and the practical reason to choose it over the alternatives. Include an install command only when it is valid for the user's environment.

If no suitable skill exists, say so and continue with the task using the available general capabilities rather than blocking on discovery.

## 5. Install only when asked

When the user explicitly wants installation and the environment supports it, use the appropriate installer, commonly:

```bash
npx skills add <owner/repo@skill> -g -y
```

When the environment cannot run the installer, provide or perform the closest supported integration path instead of claiming installation succeeded.

## Source note

This skill is adapted for this repository from the open `find-skills` workflow published by Vercel Labs: https://github.com/vercel-labs/skills/tree/main/skills/find-skills
