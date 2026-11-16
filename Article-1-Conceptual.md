# How AI Productivity Tools Turn Instructions into Drafts

A meeting transcript can contain decisions, tasks and unresolved questions in the same paragraph. An AI productivity tool can organize that material into action items in seconds. The person reading the output still needs to check who actually agreed to do the work. That distinction matters when comparing ChatGPT, Gemini and Copilot.

## Why these tools are useful

Summaries, notes, comparisons and emails involve repeated work: extracting details, shaping them into a readable format and adapting them to an audience. A language model can turn the same input into several useful formats. A student might summarize a reading, a project team might organize meeting notes, and an event coordinator might draft an invitation from confirmed details.

## How the workflow works

**Source material and instructions → chat interface → language model → generated draft → human verification**

The interface collects the prompt. The prompt specifies the task, provides the source material and sets constraints such as word count or table columns. A language model generates text one token at a time using the context available to it. A tool with access to external sources may retrieve additional information when those features are used. The comparison in the companion article supplies all sources directly.

The working components are the input, the prompt, the model, the interface and the verification step. A clear prompt can ask for an Action, Owner and Due table and instruct the model to use “Not specified” when the transcript lacks an owner. The reviewer then compares the generated rows against the transcript.

## Advantages and limitations

These tools produce structured drafts quickly, and the same prompt can be reused across platforms. Their answers can also omit a condition, infer a detail that was never provided or give a correct recommendation for the wrong reason. A numerical comparison therefore needs arithmetic checks as well as a review of the recommendation. For sensitive tasks, account data controls and permission to share the source material also matter.

An AI response time measures one stage of the workflow. To measure productivity, include the time spent preparing input, verifying claims and editing the output, then compare the total with doing the same task manually.

## Future scope

A stronger evaluation would test new inputs across several runs, verify each answer against a reference and record manual and assisted completion times. Products could also make verification easier by tying extracted claims to source passages and flagging missing information for the reviewer.

## References

- Vaswani et al. (2017), [Attention Is All You Need](https://arxiv.org/abs/1706.03762), for the Transformer architecture.
- Topic 79 practical comparison and its experiment log, available in this assignment folder.

- [NIST Generative AI Risk Management Profile](https://nvlpubs.nist.gov/nistpubs/ai/NIST.AI.600-1.pdf). Defines confabulation and explains why generated claims require verification.
- Liang et al., [Holistic Evaluation of Language Models](https://arxiv.org/abs/2211.09110). A research framework for comparing language models across tasks and evaluation metrics.
- [Stanford HELM Classic](https://crfm.stanford.edu/helm/classic/latest/). Shows how evaluation results can be organized by scenario, including summarization and information extraction.
- [Microsoft Copilot Privacy FAQ](https://support.microsoft.com/en-us/microsoft-copilot/privacy-faq-for-microsoft-copilot). Explains where to find privacy guidance for different Copilot experiences.
