# Exploratory Math Research

English · [简体中文](README.zh-CN.md) · [日本語](README.ja.md)

An experimental agent skill for open mathematical research: preserve the original problem, reconsider self-imposed constraints, and reduce premature abandonment, goal drift, and loss of purpose during delegation.

This is a collection of research guidance and worked cases distilled from internal trials. It has not undergone a controlled evaluation of effectiveness.

## What it does

- Keeps the user's objective separate from a model's chosen representation, intermediate lemma, or preferred deliverable.
- Helps turn a failed construction into a concrete next mathematical action by examining exactly which conditions failed.
- Encourages simple comparisons before expensive computation, auxiliary engineering, or proofs that no longer serve the question.
- Preserves the original purpose, formulas, established facts, and failure scope across authorized delegation and handoffs.

It is intended for genuine exploration of open problems and for reviews that affect subsequent research decisions. Ordinary exercises, transcript organization, and literature summaries without research judgment do not need this skill.

## Use

Install from GitHub with the community skills CLI:

```sh
npx skills add isshiki-works/exploratory-math-research
```

Alternatively, copy the complete `exploratory-math-research` folder to a skills location recognized by your agent. Keep `SKILL.md` at the folder root. In a host supporting named skills, start with:

```text
Use $exploratory-math-research to investigate this problem:
[problem statement, permitted assumptions, existing work, and resource limits]
```

For a review, explicitly ask to review rather than resume the research. The skill does not authorize additional agents, external actions, or a larger budget.

The default entry point is the Chinese original. The complete execution text and all 18 core cases are also available in [English](SKILL.en.md) and [Japanese](SKILL.ja.md). To use one as the entry point, copy that file over `SKILL.md` **in your installation copy**; keep the remaining files alongside it. The matching optional UI metadata are `agents/openai.en.yaml` and `agents/openai.ja.yaml`; copy the chosen file over `agents/openai.yaml` if desired. Back up an existing installation before replacing it.

The longer [historical research notes](references/discovery/index.md) are currently in Chinese. They supplement the complete core cases; they are not required translation files. No runtime dependency is needed to read the skill. Tools used for actual research depend on the task.

## Author's statement

Isshiki（一色）

As a science fiction writer, I developed this skill through repeated internal research on open problems, including constrained reproductions of work on the Jacobian problem. During these runs, I observed recurring patterns of premature abandonment, goal drift, and losses in the design of agent handoffs, and worked with Astra to try to mitigate them. I am sharing it as a preliminary approach, containing concrete, detailed suggestions for mathematical work drawn from selected historical cases. It is better suited to genuinely open problems.

It still depends on choosing the initial direction more accurately and making the right bets. This means that prompts of this kind cannot close the advantage held by institutional research, even when that research is inefficient. Even more detailed heuristics cannot progressively capture every possible path. They can only try to reduce some conspicuously unreasonable investments of effort and mistakes—while leaving open the possibility that what we dismiss may actually be right. On that basis, I hope the skill can improve the ability of currently accessible models to choose relevant routes, reduce premature abandonment, and reduce excessive investment in irrelevant proofs merely to deliver an answer.

A discriminating A/B evaluation has not been completed. Measuring how much this skill improves performance, as one might evaluate Ponytail, would consume a substantial number of tokens. I currently have neither the capacity nor plans to set aside sufficient compute for a comprehensive evaluation. The skill distills experience and lessons from several internal challenges on open mathematical problems. We did not use it to solve the problems we had originally hoped to tackle, but the patterns of success and failure identified in a small set of Jacobian reproductions already provide preliminary support for the existence of these issues.

On September 8, 2026, OpenAI announced a solution to the Navier–Stokes existence and smoothness problem and released a paper and a Lean formalization. This comes close to the clearest fulfillment of what this skill and my related work had predicted. As an early AI user and a science fiction writer, I feel anxious about these developments, particularly the unprecedented concentration of control over frontier knowledge in a few large AI companies.

I hope this work can help everyone willing to use, question, and help build this skill. Much of it comes from human mathematical insight and knowledge accumulated over time. At this moment of change, I hope we can come together, share the results and experience we already have as widely as possible, and reduce pointless waste and enclosure. Together, we must face a new reality: the new era is not in the future. It begins now.

## Evidence and dates

The public mathematical cases are sources of methods and insight. They are not discoveries made by this project, and their correctness does not establish the skill's effectiveness. Internal reproductions had prompts and shared context; they are not independent, unprompted trials. Cross-model and cross-language behavioral equivalence have not been measured.

Document revision: **2026-09-09**. Recent source dates and status are recorded in [source notes](SOURCE_NOTES.md). Publication dates, manuscript dates, and the date a source was checked are separate. These documents do not promise automatic tracking of later developments.

## Contribute and license

Corrections, translations, examples of failures, and affordable comparisons are welcome. See [contributing](CONTRIBUTING.md). Once hosted on GitHub, use the repository's issues and pull requests for discussion.

[MIT](LICENSE), copyright © 2026 Isshiki（一色）. The project is independently maintained and is not affiliated with OpenAI, Anthropic, or the authors of the cited work. Linked papers and posts retain their own terms; this repository does not relicense them.
