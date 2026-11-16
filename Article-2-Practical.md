# Comparing ChatGPT, Gemini and Copilot on Four Productivity Tasks

A printing comparison can name the cheapest shop and still give incorrect reasoning. That happened in the Topic 79 experiment, which tested how well three browser assistants turned the same material into usable work.

## Problem and tools

The goal was to compare ChatGPT, Google Gemini and Microsoft Copilot on summarization, note-taking, source-based research and writing. The experiment used their browser interfaces, one shared prompt and a structured comparison log.

## Workflow

**Common prompt → fresh chat in each tool → draft response → capture output → check against the same criteria**

## Steps to reproduce

1. Open the companion prompt.txt file. It contains an AI paragraph, a fictional workshop transcript, three synthetic printing extracts and instructions for an announcement email.
2. Start a fresh chat in each tool and send the same four-task prompt. Use the supplied materials as the source for each answer.
3. Save the first complete outputs. Check summary length, meeting decisions and action owners, printing arithmetic and email requirements.
4. For a separate timing run, start from a fresh chat again. Measure from Send to the first browser observation that confirms the full response has finished. Record the time for the four tasks together.
5. Enter the observations in comparison_log.csv and retain screenshots of the original outputs.

## Outputs and observations

| Task | Observed result |
|---|---|
| Summarization | All three met the three-bullet format. |
| Note-taking | All three captured two decisions and three actions and preserved the unassigned reminder owner. |
| Source comparison | All three selected Library Print at Rs 210. Gemini showed the Rs 240 Campus Desk total and explained that two orders were needed. Copilot showed the total and left the split implicit. ChatGPT incorrectly described Campus Desk as cheaper per page. |
| Email | ChatGPT produced 81 words, Gemini 90 and Copilot 92. All included the confirmed workshop details. |

![Gemini's source comparison](assets/gemini-task3.jpg)

![ChatGPT's source comparison](assets/chatgpt-task3.jpg)

*Figures show the original browser outputs from the quality trial.*

The separate timing follow-up observed **5.86 seconds for ChatGPT, 7.56 seconds for Copilot and 10.42 seconds for Gemini**. Each value covers the entire four-task response in one accepted run. A manual baseline and review time were unmeasured, so actual time savings remain unknown.

## Challenges and lessons

The completion control differed across sites, so the timed run used each site's visible completion signal. The research task used synthetic excerpts, which made arithmetic and source claims checkable and kept the test focused on evidence synthesis. The sample was small, and account-specific access and subscription limits can affect reproducibility. The workshop data was fictional to avoid exposing private details.

For these inputs, all three were useful for summaries and meeting notes. Gemini required the least clarification on the printing comparison. When using an AI draft to make a decision, check the calculation and operational restrictions before acting on its recommendation.

## References

- [Shared four-task prompt](prompt.txt). Exact input used across the three tools.
- [Topic 79 comparison log](comparison_log.csv). Primary record for the quality observations and browser timings.
- [Gemini evidence](assets/gemini-task3.jpg) and [ChatGPT evidence](assets/chatgpt-task3.jpg). Original printing-task screenshots.
- Liang et al., [Holistic Evaluation of Language Models](https://arxiv.org/abs/2211.09110). Background for comparing tools across multiple tasks and publishing inputs and outputs.
- [Stanford HELM Classic](https://crfm.stanford.edu/helm/classic/latest/). Examples of task-specific evaluation metrics.
- [NIST Generative AI Risk Management Profile](https://nvlpubs.nist.gov/nistpubs/ai/NIST.AI.600-1.pdf). Background on checking plausible but inaccurate AI output.
- [Microsoft Copilot Privacy FAQ](https://support.microsoft.com/en-us/microsoft-copilot/privacy-faq-for-microsoft-copilot). Product guidance for the privacy discussion.
