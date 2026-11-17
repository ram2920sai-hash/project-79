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

## Core theory

### Language models and tokens

A language model represents text as tokens, which may be words, parts of words or punctuation. It uses the available context to estimate which token should come next, then repeats this process to build a response. Transformer models use attention to relate tokens to one another, which helps them connect instructions with details scattered across a document. A fluent response still needs verification against its source. [Transformer paper](https://arxiv.org/abs/1706.03762)

### Prompts, context and grounding

A prompt defines the task, source material and output format. The context is the material available for the current response, which may include earlier chat messages and supplied documents. Grounding means tying the answer to evidence in those sources. For example, when extracting meeting actions, “Not specified” is the correct owner if the transcript names nobody. That rule preserves a gap that the human reviewer can resolve.

### Four productivity tasks and their checks

- **Summarization** compresses information. Check that the main ideas survived and that the tool added no unsupported claims.
- **Note-taking** turns discussion into decisions and actions. Check names, dates, commitments and open questions against the transcript.
- **Source-based research** compares claims and evidence. Check calculations, source labels and conditions that affect the result.
- **Writing** adapts facts for an audience. Check tone, word count and whether the draft accidentally introduces new commitments.

### Main points

- **Give every tool the same input and criteria** when comparing outputs.
- **Verify claims with source evidence** before acting on a draft.
- **Measure the whole workflow** if the goal is to estimate time savings.

## Future scope

A stronger evaluation would test new inputs across several runs, verify each answer against a reference and record manual and assisted completion times. Products could also make verification easier by tying extracted claims to source passages and flagging missing information for the reviewer.

## Inside a language model

### Tokenization and embeddings
A tokenizer maps text fragments to integer IDs. A model looks up a learned vector for each ID. These vectors are called embeddings. The model also receives information about token position, because changing the order can change the meaning. For example, “Arun assigned Mina” and “Mina assigned Arun” share the same words but describe different responsibilities.

### Self-attention and the Transformer block
Each token representation is projected into a query, a key and a value. A query is compared with keys to determine how strongly earlier tokens should influence the current representation. The resulting weights combine the value vectors. A causal mask prevents the model from using future tokens during next-token prediction. Multiple attention heads provide different learned projections. Feed-forward layers transform each token representation, and residual connections and normalization help information pass through successive layers. [Transformer paper](https://arxiv.org/abs/1706.03762)

### Training, inference and decoding
During training, a language model adjusts its parameters to improve predictions across examples. At inference time, the model uses the current prompt and generated text to calculate scores for possible next tokens. A decoding rule chooses a token and the cycle repeats. Sampling can produce different drafts from the same prompt. Repeating a test therefore helps distinguish an occasional outcome from a recurring pattern.

### Context limits and external evidence
The context window limits how much material the model can process at once. A long conversation may leave less space for a new source document and its answer. Retrieval can help by selecting relevant passages and placing them in the prompt. Retrieval quality and generation quality are distinct. A tool can retrieve the right paragraph and still misinterpret it, or produce a polished answer using the wrong paragraph.

## How to design a reliable productivity workflow

### Separate extraction, transformation and verification
In meeting notes, extraction identifies the stated tasks and owners. Transformation organizes them into a consistent table. Verification checks each row against the transcript. Keeping these stages visible makes it easier to diagnose a mistake. If an owner appears without support, trace the error to extraction or inference before improving the wording of the final table.

### Design outputs around evidence
Specify the source boundary, the requested format and how to handle missing information. A useful instruction for a printing comparison is to show the rate, quantity, fixed fee and order limit for each provider. This exposes the assumptions behind the recommendation. For a workshop email, supply the confirmed date, location and audience, then ask the tool to flag missing details before drafting.

### Why fluent answers can still contain errors
Next-token prediction can produce language that resembles a valid explanation even when a premise is wrong. In an arithmetic task the best check is to recompute the total. In a summary, compare each important claim with its source passage. In an email, look for invented deadlines, promises or eligibility rules. The type of task determines the most useful review method. [NIST Generative AI Profile](https://nvlpubs.nist.gov/nistpubs/ai/NIST.AI.600-1.pdf)

### Evaluation and future scope
A stronger evaluation would use several examples per task, verified reference answers and independent reviewers. It would also test whether outputs remain useful when inputs contain ambiguous dates, conflicting quotes or incomplete details. A provenance feature could connect each extracted claim to a source passage, reducing the effort required to verify the draft. [HELM evaluation framework](https://arxiv.org/abs/2211.09110)

## References

- Vaswani et al. (2017), [Attention Is All You Need](https://arxiv.org/abs/1706.03762), for the Transformer architecture.
- Topic 79 practical comparison and its experiment log, available in this assignment folder.

- [NIST Generative AI Risk Management Profile](https://nvlpubs.nist.gov/nistpubs/ai/NIST.AI.600-1.pdf). Defines confabulation and explains why generated claims require verification.
- Liang et al., [Holistic Evaluation of Language Models](https://arxiv.org/abs/2211.09110). A research framework for comparing language models across tasks and evaluation metrics.
- [Stanford HELM Classic](https://crfm.stanford.edu/helm/classic/latest/). Shows how evaluation results can be organized by scenario, including summarization and information extraction.
- [Microsoft Copilot Privacy FAQ](https://support.microsoft.com/en-us/microsoft-copilot/privacy-faq-for-microsoft-copilot). Explains where to find privacy guidance for different Copilot experiences.




## Advanced theory and applications

### From a prompt to a probability distribution

At each decoding step, the final model layer produces a numerical score for every possible next token. A softmax operation converts those scores into probabilities. Temperature changes how sharply those probabilities favor the highest-scoring tokens. Lower temperatures can make wording more predictable, while higher temperatures can widen the range of plausible continuations. Products may hide these settings, so a browser comparison records the behavior of the interface and its defaults.

### What attention actually computes

Scaled dot-product attention multiplies queries by transposed keys, divides the result by the square root of the key dimension, and applies softmax before combining the values. The scaling helps keep the scores from growing too large. For a workshop transcript, attention gives the model a way to relate a name in one sentence to a due date in another. Whether it connects them correctly still depends on the learned parameters and the context. [Transformer paper](https://arxiv.org/abs/1706.03762)

### Training objectives and instruction following

Next-token training teaches the model to predict continuations across many examples. Instruction tuning can then use examples of requests and desired responses to make the model more useful as an assistant. These stages explain why a model can follow a request for a table while making a mistake in one cell. Formatting and faithful extraction depend on different aspects of the response and deserve separate checks.

### Context windows, truncation and retrieval

A context window has a finite token budget. Source text, conversation history and generated output all use some of that budget. When a source is very long, one workflow retrieves relevant sections and gives them to the model. Another divides the document into sections and combines partial summaries. Retrieval can miss a relevant passage, while partial summaries can lose relationships that cross section boundaries. Both workflows need checks against the original material.

### Extractive and abstractive summarization

An extractive summary selects sentences or phrases from the source. An abstractive summary restates ideas in new language. Extraction can make verification easier, although selected sentences may depend on context that was left out. Abstraction can improve readability and brevity, but the reviewer needs to check whether paraphrasing changed certainty, scope or meaning. For example, “registration may close Friday” conveys a different commitment from “registration closes Friday.”

### Structured extraction and missing values

An action table can define separate fields for task, owner, deadline and status. Each field should have a consistent meaning. An explicit missing value helps distinguish an unassigned action from an action whose owner was accidentally omitted. Validation can check that every row has the expected columns. A source check is still needed to determine whether the values inside those columns are accurate.

### Human review and accountable use

Review effort should reflect the consequence of an error. A draft workshop announcement needs a check against confirmed dates, venue and contact details. A cost comparison needs independently recalculated totals and a check of conditions such as minimum quantities. For shared work, keep a record of which information came from the source and who approved the final version. [NIST Generative AI Profile](https://nvlpubs.nist.gov/nistpubs/ai/NIST.AI.600-1.pdf)
