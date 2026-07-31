# Neural.network
OpenAI GPT-5.6 launched in July 2026 with three distinct models—Sol, Terra, and Luna—each optimized for different workloads, performance levels, and cost tiers.
Release Timeline and Access
GPT-5.6 was initially launched on June 26, 2026, as a limited preview restricted to roughly 20 government-approved organizations due to a U.S. federal review process for AI safety and cybersecurity compliance. The broad public release occurred on July 9, 2026, making all three models accessible to paid ChatGPT plans and via the API. This marked the first time OpenAI’s commercial model rollout was directly influenced by government oversight.
Model Variants and Use Cases
Sol: The flagship model, designed for complex coding, cybersecurity, biology research, and agentic workflows. It supports Ultra Mode, which spawns parallel subagent processes for complex reasoning, improving benchmark performance (e.g., Terminal-Bench score from 88.8% to 91.9%), Sol is priced at $5 per million input tokens and $30 per million output tokens. Terra: A mid-tier, balanced model designed for standard professional and developer use cases at a lower cost overhead.Luna: The most cost-efficient, high-volume tier optimized for speed and structured, repetitive tool-calling agent loops. Pricing and UpdatesAPI Cost Adjustments: Following the July 30 price cuts, Luna input/output costs dropped significantly (to $0.20 / $1.20 per million tokens), while Terra was reduced by 20%. Sol pricing remained at its baseline ($5 input / $30 output per million tokens).Ultra Mode: A high-capability setting introduced alongside the models to coordinate multiple parallel subagents for demanding jobs. 
Practical Implications
GPT-5.6 introduces a tiered model strategy, allowing developers and enterprises to select models based on intelligence, speed, and cost, rather than a single flagship approach. The government-gated preview ensured safety and compliance, particularly in cybersecurity-sensitive applications, before broader public access This release also signals OpenAI’s shift toward permanent capability tiers that can be updated independently, providing flexibility for future improvements.
In summary, GPT-5.6 represents a major evolution in OpenAI’s model strategy, offering specialized models for different workloads, enhanced reasoning capabilities, and enterprise-focused features, all while navigating government oversight and safety considerations. GPT-5.6 introduces a revamped caching system with explicit developer control:

Cache writes: 1.25x the standard input price
Cache reads: 90% discount on standard input price
Minimum cache lifetime: 30 minutes
Explicit breakpoints: You define where cache boundaries sit in your prompts
This is a meaningful improvement over implicit caching. You can now structure your prompts with stable prefixes (system instructions, context documents) and mark breakpoints so those sections get cached reliably. The 90% read discount means that for repeated calls with similar prefixes, your effective input cost drops dramatically.

For Sol at $5/1M input tokens: cache writes cost $6.25/1M, but subsequent reads cost just $0.50/1M. If you are making 10+ calls with the same prefix within 30 minutes, the math works out heavily in your favor. Access: The Government Gate
This is the part that matters most for practical planning. GPT-5.6 is not available through normal channels.

No ChatGPT integration
No public API waitlist
No self-serve access of any kind
Approximately 20 trusted partners have access
The US government decides who gets added
OpenAI previewed GPT-5.6’s capabilities to the US government ahead of launch, at the government’s request. This is the second frontier model in a month to face government restrictions, following the Fable 5 ban.

For most developers reading this, GPT-5.6 is not something you can use today. Plan accordingly. If you need frontier-level performance right now, Claude Sonnet 5 launched June 30 at $2/$10 and is publicly available.Safety Stack
The access restrictions exist because of GPT-5.6’s capabilities in sensitive domains. OpenAI invested 700,000 A100-equivalent GPU hours in automated red-teaming and reports the following scores:

Virology Capabilities Test: 53.5%
Molecular Biology: 60%
Human Pathogen: 68.4%
ExploitBench: Competitive with Mythos Preview at 1/3 the output tokens
The safety architecture is three-layered:

Model-level training: Safety behaviors baked into the model weights
Real-time classifiers: External systems that monitor inputs and outputs
Account-level review: Human oversight of partner organizations
This is the most restrictive safety deployment OpenAI has ever done, and it reflects the broader trend toward AI model supply chain risks being taken seriously at the policy level.
1. Context Window: Up to 1.5 Million Tokens
GPT-5.5 operates with a context window that most production applications have treated as ~400K tokens effective for complex tasks. GPT-5.6 is expected to push this to approximately 1.5 million tokens—a 43% increase over the developer-reported ceiling for 5.5.

Why this matters: long-context handling is one of the clearest capability signals in the current frontier race. Claude Fable 5 and Gemini 3.1 Pro have both pushed long-context as a differentiator. A 1.5M token GPT model changes the calculus for use cases like full-codebase analysis, book-length document review, and multi-session agent state persistence.

At 1.5M tokens you can fit roughly:

An entire mid-size software project's worth of source code
A legal document corpus for a full case discovery process
Several full academic papers plus all their cited sources
Hours of meeting transcripts from a long project
2. Agentic Task Completion: Meaningful Reliability Gains
The most technically significant expected improvement is in multi-hour agentic task completion rates—particularly for Codex Computer Use workloads where an AI agent plans, executes, debugs, and iterates on a task autonomously over extended time horizons.

GPT-5.5 made progress here with its 82.7% Terminal-Bench 2.0 score, but early reports suggest GPT-5.6's agentic reliability improvement is meaningful enough that developers noticed it without being told the model changed. The improvement is attributed to:

A cleaner reward signal in training that reduces reward hacking in long agent loops
Tighter persona-isolation (the model less frequently "breaking character" or contradicting its system prompt mid-task)
An improved SFT pipeline that doesn't recycle contaminated rollouts—a subtle but important training quality fix that affects how reliably the model follows complex multi-step instructions
For developers building with Codex or custom agent frameworks, this kind of reliability improvement matters more than raw benchmark scores. A 10% improvement in task completion rate on a 20-step agent pipeline means the agent succeeds more than twice as often end-to-end.

3. Refreshed Training Data Through Mid-2026
GPT-5.5 launched in April 2026 with a training cutoff that left a gap for events from early 2026 onward. GPT-5.6 is expected to include training data through approximately May 2026, closing this window.

For most tasks, training cutoff doesn't matter. For tasks involving recent software ecosystems (new library releases, framework updates), recent world events, or current competitive intelligence, a model trained 6–8 weeks more recently is meaningfully more useful.

4. FrontierMath Tier 4 Reasoning
GPT-5.5 posted 35.4% on FrontierMath Tier 4—the hardest mathematical reasoning benchmark. GPT-5.6 is expected to show improvement here, potentially pushing past 40%. This would be the most direct counter to OpenAI's o3-pro positioning as the reasoning-first model: if GPT-5.6 meaningfully improves frontier math without being explicitly a "reasoning model," it blurs the product line distinction.

5. Token Efficiency for Long Tasks
For long-running agentic sessions, GPT-5.6 reportedly uses fewer tokens to accomplish the same work—a result of the cleaner SFT pipeline reducing repetition, self-correction loops, and unnecessary verbosity. For API users with high-volume agentic workloads, this efficiency gain translates directly to lower cost even if per-token pricing stays the same.

Sources and references (APA-style):

OpenAI. (2026, July 9). GPT‑5.6: Frontier intelligence that scales with your ambition. OpenAI. https://openai.com/index/gpt-5-6/

TechCrunch. (2026, July 9). OpenAI launches its new family of models with GPT‑5.6. TechCrunch. https://techcrunch.com/2026/07/09/openai-launches-its-new-family-of-models-with-gpt-5-6/

CNBC. (2026, July 8). OpenAI to publicly release GPT‑5.6, rolls out Live voice AI models. CNBC. https://www.cnbc.com/2026/07/08/openai-expanding-gpt-5point6-ai-model-release-ending-government-limits.html

GitHub Blog. (2026, July 9). OpenAI’s GPT‑5.6 Sol, Terra, and Luna are now available in GitHub Copilot. GitHub. https://github.blog/changelog/2026-07-09-openais-gpt-5-6-sol-terra-and-luna-are-now-available-in-github-copilot/

AWS Machine Learning Blog. (2026, July 9). OpenAI GPT‑5.6 Sol, Terra, and Luna are now generally available on Amazon Bedrock. https://aws.amazon.com/blogs/machine-learning/openai-gpt-5-6-sol-terra-and-luna-are-now-generally-available-on-amazon-bedrock/

DataCamp. (2026, July). GPT‑5.6 Sol, Terra, and Luna: OpenAI's Next-Gen Model Family. DataCamp. https://www.datacamp.com/blog/gpt-5-6-sol-luna-terra

ExplainX.ai. (2026, July). GPT‑5.6: Rolling Out July 9 — Sol, Terra, Luna. https://www.explainx.ai/blog/gpt-5-6-release-date-features-benchmarks-2026

(When you add AI session logs where an LLM recommended addition
