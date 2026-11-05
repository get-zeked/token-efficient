# token-efficient

A single skill for Perplexity Computer that cuts routine tool commentary while keeping the result, its evidence, and anything the user needs to act. Ask for a detailed explanation, a particular format, or a source list whenever you need one.

## Install and use

1. Open [SKILL.md](SKILL.md) and choose **Download raw file**.
2. In Perplexity Computer, open **Skills → Create skill → Upload a skill** and select the file.
3. In a task, ask: “Use token-efficient. Compare these two reports and cite the differences.” Computer can also select a skill when the task matches its description. See [Perplexity Academy's guide to Skills](https://www.perplexity.ai/en-GB/hub/academy/how-to-use-computer-skills).

For another [Agent Skills](https://agentskills.io/specification) client, place the file in a folder named `token-efficient` under that client's skills directory. For the Claude Code original, see [drona23/claude-token-efficient](https://github.com/drona23/claude-token-efficient).

## What to expect

| Try it with | Expected behavior |
| --- | --- |
| “Look up one value in this CSV.” | Read the relevant field and answer directly. No task list or subagent for a one-call lookup. |
| “Write the report and hand it to the next agent.” | Keep citations in the report. Give the next agent the exact path, even if the file is already visible to the user. |
| “The upload timed out. Did it go through?” | Check the destination before retrying. If the status is still unknown, say so. Report the useful error without exposing credentials. |
| “Explain the calculation step by step.” | Give the requested steps. Brevity does not override the deliverable. |

[Issue #1](https://github.com/get-zeked/token-efficient/issues/1) contains the model reviews behind v2. The full skill file, including frontmatter, went from 1,206 tokens in v1 to 385 in v2 (68% smaller, measured with `tiktoken`'s `o200k_base` encoding). This measures the instructions only. It does not predict Perplexity session usage or billing.

## Credits and license

Adapted by get-zeked from [drona23/claude-token-efficient](https://github.com/drona23/claude-token-efficient) by Drona Gangarapu. [MIT license](LICENSE).
