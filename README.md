# Awesome Proactive Agents [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

> A curated list of proactive agents: systems that decide whether, when, and how far to help without a new explicit request.

Primary sources were checked on 2026-11-09. A resource is listed only when a paper, official repository, or author-hosted page shows that behavior. An agent that waits for a goal and then uses tools is not included merely because it is called proactive.

## What Counts

A proactive agent takes initiative with a person or a shared situation. It may anticipate a need, speak or act before it is asked, request missing information before proceeding, or stay silent when intervention is not warranted.

**Include** a resource when at least one of these is true:

- The system can act, speak, or prepare help before a new explicit request, and it has a real option to do nothing.
- The work evaluates timing, interruption cost, user acceptance, or the content of an unrequested intervention.
- A benchmark's labels require anticipating a need or choosing when to intervene.

**Leave out:**

- Reactive tool-use, coding, or research agents that run only after a user assigns the goal.
- Uses of "proactive" that mean exploration, self-checking, or a tougher security posture.
- Self-evolving training loops and agentic ML workflows. Those belong in the related lists below.
- Product pages and announcements that do not have a technical primary source.

## Contents

- [What Counts](#what-counts)
- [Surveys and Foundations](#surveys-and-foundations)
- [Benchmarks and Evaluation](#benchmarks-and-evaluation)
- [Intervention Decisions](#intervention-decisions)
- [Anticipation, Memory, and Context](#anticipation-memory-and-context)
- [Dialogue and Collaboration](#dialogue-and-collaboration)
- [Studies of Proactive Support](#studies-of-proactive-support)
- [Safety and Deployed Systems](#safety-and-deployed-systems)
- [Related Lists](#related-lists)
- [Contributing](#contributing)

## Surveys and Foundations

- **Foundations of Proactive Agents: Principles, Technical Layers, and Proactivity-Gym** (Jio Oh et al., 2026) - Design principles for proactive LLM agents that use idle compute before a user asks: task capability, temporal allocation, and trust, plus the Proactivity-Gym project. [[arXiv]](https://arxiv.org/abs/2609.37267) [[Project]](https://harryoh99.github.io/foundations_of_proactive_agents/)
- **Proactive Service Agents: A Unified Decision Framework, Methods, and Evaluation** (Yan Tang et al., 2026) - Survey that treats proactive service as inferring an opportunity from incomplete signals and choosing among staying silent, asking, assisting, and acting. [[arXiv]](https://arxiv.org/abs/2609.03727)
- **Agentic Coding Needs Proactivity, Not Just Autonomy** (Bui, 2026) - Position paper separating proactivity from autonomy for coding agents: noticing a relevant change before the developer asks, and deciding whether to surface it. [[arXiv]](https://arxiv.org/abs/2605.06717)
- **Knowing Isn't Understanding: Re-grounding Generative Proactivity with Epistemic and Behavioral Insight** (Kaur et al., ICML 2026) - Argues that proactivity matters when users cannot yet say what is missing, and that unrequested interventions can also misdirect or overwhelm them. [[arXiv]](https://arxiv.org/abs/2602.15259)
- **Proactive Agent: Shifting LLM Agents from Reactive Responses to Active Assistance** (Lu et al., 2024) - Learns to propose tasks without an explicit instruction from human accept/reject labels, and releases ProactiveBench with 6,790 events. This events dataset is not the ECCV 2026 ProactiveBench below. [[arXiv]](https://arxiv.org/abs/2410.12361) [[GitHub]](https://github.com/thunlp/ProactiveAgent)
- **A Survey on Proactive Dialogue Systems: Problems, Methods, and Prospects** (Deng et al., IJCAI 2023) - Survey of conversational agents that steer a dialogue toward a system-side target or goal. [[arXiv]](https://arxiv.org/abs/2305.02750) [[Reading list]](https://github.com/dengyang17/ProactiveDialogues)
- **Planning for Proactive Assistance in Environments with Partial Observability** (Kulkarni et al., 2021) - Plans assistance in a shared environment so the action lowers the human's task cost and the human can tell that it does. [[arXiv]](https://arxiv.org/abs/2105.00525)
- **Principles of Mixed-Initiative User Interfaces** (Horvitz, 1999) - Principles for an interface agent that senses activity and chooses among acting, asking, and deferring, using the cost of interrupting the user; demonstrated with the LookOut scheduling assistant. [[PDF]](https://erichorvitz.com/chi99horvitz.pdf)

## Benchmarks and Evaluation

- **HALO: Human-Grounded Granular Evaluation of Proactive Agents** (Pei et al., 2026) - Expert judgments of whether assistance is warranted, when it should happen, and how far it should go, over personal environments that require evidence before an intervention. [[arXiv]](https://arxiv.org/abs/2610.39086) [[GitHub]](https://github.com/CedricPei/HALO)
- **Omni-InteractScope: Benchmarking Proactive and Agentic Interaction in Continuous Omnimodal Streams** (Yinsong Yan et al., 2026) - Human-annotated interactions over continuous audiovisual streams, including query-free assistance and event-timed tool use. [[arXiv]](https://arxiv.org/abs/2610.35439) [[Project]](https://yinsongyan.github.io/Omni-InteractScope/)
- **When Should AI Chime In? Benchmarking Timely Contribution of Proactive Agents in Multi-Party Chat** (Ruotong Wang et al., 2026) - PITCH isolates timing: given a candidate contribution, participants in the same unscripted multi-party chat judge when it should be inserted. [[arXiv]](https://arxiv.org/abs/2610.25896)
- **ProEvent: An Event-centric Benchmark for Proactive Agents** (Guanzhen Li et al., 2026) - Tests whether an agent maintains upcoming events from ongoing chats so it can assist around those events without a new instruction. [[arXiv]](https://arxiv.org/abs/2607.17701)
- **VitaBench 2.0: Evaluating Personalized and Proactive Agents in Long-Term User Interactions** (Chen et al., 2026) - Long-horizon personalization benchmark whose proactivity tasks require recognizing missing information and acquiring it before a decision. [[arXiv]](https://arxiv.org/abs/2605.27141) [[GitHub]](https://github.com/meituan-longcat/VitaBench-2.0) [[Project]](https://vitabench2.github.io/)
- **From Reactive to Proactive: Assessing the Proactivity of Voice Agents via ProVoice-Bench** (Xu et al., 2026) - Voice-agent benchmark, submitted to Interspeech 2026, for proactive intervention and monitoring rather than reply-only conversation. [[arXiv]](https://arxiv.org/abs/2604.15037)
- **Proactive Agent Research Environment: Simulating Active Users to Evaluate Proactive Assistants** (Nathani et al., 2026) - Pare models applications as stateful machines so a simulated user stays active while an assistant is tested; Pare-Bench has 143 tasks. [[arXiv]](https://arxiv.org/abs/2604.00842)
- **ProactiveBench: Benchmarking Proactiveness in Multimodal Large Language Models** (De Min et al., ECCV 2026) - Tests whether a multimodal model asks a person for a simple intervention, such as removing an occlusion, instead of answering from incomplete evidence. [[arXiv]](https://arxiv.org/abs/2603.19466) [[GitHub]](https://github.com/tdemin16/proactivebench) [[Dataset]](https://huggingface.co/datasets/tdemin16/ProactiveBench)
- **ProAgentBench: Evaluating LLM Agents for Proactive Assistance with Real-World Data** (Yuanbo Tang et al., 2026) - Splits proactive assistance into timing prediction and content generation, using 28,000+ events from 500+ hours of real user sessions. [[arXiv]](https://arxiv.org/abs/2602.04482)
- **ProMediate: A Socio-cognitive framework for evaluating proactive agents in multi-party negotiation** (Ziyi Liu et al., 2025) - Simulation testbed and measures for a mediator that steps into multi-party, multi-topic negotiation. [[arXiv]](https://arxiv.org/abs/2510.25224) [[GitHub]](https://github.com/microsoft/ProMediate-Eval)
- **ProactiveEval: A Unified Evaluation Framework for Proactive Dialogue Agents** (Tianjian Liu et al., 2025) - Splits proactive dialogue into target planning and dialogue guidance, with 328 evaluation environments across 6 domains. [[arXiv]](https://arxiv.org/abs/2508.20973) [[GitHub]](https://github.com/liutj9/ProactiveEval)
- **Omni-Life: Benchmarking Omnimodal Real-Time AI Assistants in People's Daily Lives** (Hong et al., 2026) - Scores whether a real-time audiovisual assistant should help, including 555 required intervention events and 110 videos that should stay silent throughout. [[arXiv]](https://arxiv.org/abs/2611.02835) [[GitHub]](https://github.com/todayai-labs/omni-life) [[Project]](https://todayai-labs.github.io/omni-life/)

## Intervention Decisions

- **AskStream: When and What to Ask Proactively under Uncertainty in Streaming Video Understanding** (Lu Wang et al., 2026) - Gives a streaming video model a third action, ask, so it can request missing information instead of waiting forever or answering anyway. [[arXiv]](https://arxiv.org/abs/2610.38678) [[GitHub]](https://github.com/wanglu-cs/AskStream) [[Project]](https://www.askstream.top)
- **Ask Less, Ask Better: Allocating User Attention in Proactive LLM Agents with Interruption Budgets** (Zhang et al., 2026) - Caps how many questions an agent may ask and adds a cost for questions that are hard to read or not worth asking. [[arXiv]](https://arxiv.org/abs/2610.24411)
- **Asking for What Was Never Requested: Horizontal and Vertical Proactivity in Agents** (Levy et al., 2026) - Scores two kinds of unrequested information seeking, and trains ProactiveInquirer to prefer the question that retrieves more of the needed evidence. [[arXiv]](https://arxiv.org/abs/2609.37236) [[GitHub]](https://github.com/dolev31/ProactiveInquirer) [[Project]](https://dolev31.github.io/ProactiveInquirer/)
- **Clarify the User or Verify the World? Uncertainty Routing for Proactive Agents** (Zhaofeng Li et al., 2026) - PROUR routes each uncertainty to one of three choices: act, clarify with the user, or verify the world. [[arXiv]](https://arxiv.org/abs/2609.32255)
- **Perceive Before Reasoning: A Pre-Reasoning Perception Framework for Efficient and Reliable Proactive Mobile Agents** (Ding et al., 2026) - A lightweight perceptor decides whether a mobile intervention is warranted before a heavier reasoner runs. [[arXiv]](https://arxiv.org/abs/2606.03236)
- **Do Proactive Agents Need an LLM to Decide When to Act?** (Xiaoze Liu et al., 2026) - A temporal graph controller chooses when to trigger help and which entities to pass in, so the language model is not rerun on every silent moment. [[arXiv]](https://arxiv.org/abs/2605.30152)
- **Anticipate and Learn: Unleashing Idle-Time Compute in Proactive Agents** (Hu et al., 2026) - ProAct predicts likely next needs during idle time and gathers evidence before the user asks; ProActEval covers 200 scenarios in 40 domains. [[arXiv]](https://arxiv.org/abs/2605.25971) [[GitHub]](https://github.com/AgentACE-AI/ProAct)
- **Pushing Forward Pareto Frontiers of Proactive Agents with Behavioral Agentic Optimization** (Yao et al., 2026) - Behavior Agentic Optimization trains multi-turn agents against the tradeoff between finishing the task and how often they ask the user. [[arXiv]](https://arxiv.org/abs/2602.11351) [[Project]](https://proactive-agentic-rl.github.io/)
- **PRISM: Festina Lente Proactivity -- Risk-Sensitive, Uncertainty-Aware Deliberation for Proactive Agents** (Fu et al., 2026) - Intervenes only when an estimated chance of user acceptance clears a threshold set from the costs of missed help and false alarms. [[arXiv]](https://arxiv.org/abs/2602.01532) [[Project]](https://prism-festinalente.github.io/)
- **Proactive Agents for Multi-Turn Text-to-Image Generation Under Uncertainty** (Hahn et al., ICML 2025) - Asks clarification questions and shows an editable belief graph when an image prompt leaves user intent underspecified. [[arXiv]](https://arxiv.org/abs/2412.06771)
- **Don't Guess, Ask Wisely: Benchmarking and Training Proactive Elicitation in Open-Domain LLM Conversations** (Rongyu Zhang et al., EMNLP 2026) - VagueBench evaluates when to ask for missing detail before answering an underspecified query, and DialogGRPO trains that choice without over-asking on complete queries. [[arXiv]](https://arxiv.org/abs/2611.01878) [[GitHub]](https://github.com/zhangrongyu0101/VagueBench) [[Project]](https://zhangrongyu0101.github.io/VagueBench/) [[Dataset]](https://huggingface.co/datasets/rongyu0101/VagueBench)
- **The Price of Scale in Proactive Memory Recall** (Yichuan Chen and Xin Wang, 2026) - Treats the choice to surface a stored memory without being asked as an interruption decision whose difficulty grows with the size of the memory store. [[arXiv]](https://arxiv.org/abs/2610.34507) [[GitHub]](https://github.com/RiverChenStillCompiling/price-of-scale)

## Anticipation, Memory, and Context

- **Prospective Memory for Proactive LLM Agents** (Bei et al., 2026) - Pro-Memory keeps future intentions separate from the decision of when a new observation makes one of them worth acting on. [[arXiv]](https://arxiv.org/abs/2611.05731)
- **Proactive Memory for Event-Driven LLM Agents** (Jinyang Li et al., 2026) - ProactMem checks recurring regularities against past events before treating a new event as a chance to act. [[arXiv]](https://arxiv.org/abs/2610.36967)
- **StreamVibe: Proactive Video Agents for Evolving User Intent** (Chengzhi Liu et al., 2026) - Infers implicit intent from a continuous video observation and changes its assistance as that intent changes, with StreamVibe-Bench. [[arXiv]](https://arxiv.org/abs/2610.34662) [[Project]](https://stream-vibe.github.io/)
- **ProMemAgent: Long-Horizon Proactive Assistance with Context-Aware Prospective Memory from Sensory Perceptions** (Xu et al., 2026) - Turns egocentric video and audio into cues for intentions that should be carried out hours or days later, not at the moment they are noticed. [[arXiv]](https://arxiv.org/abs/2610.27400)
- **An Agentic Framework for Proactive Robots with Procedural Assistance Memory** (Dohyun Lee et al., CoRL 2026) - A robot reads a memory of activity phases and assistance rules to decide when to help, instead of mapping one observation to one commonsense need. [[arXiv]](https://arxiv.org/abs/2610.21211) [[Project]](https://davian-robotics.github.io/PAM/)
- **Act2Intention: A Benchmark For Developing Active Mobile Agents Through Inferring User Intention from GUI Actions** (Xiaokai Yan et al., IMWUT) - Predicts likely next intentions from mobile GUI trajectories. The released executor performs intentions the user confirms. [[arXiv]](https://arxiv.org/abs/2608.14132) [[GitHub]](https://github.com/npuNancy/Act2Intention)
- **ProAgent: Harnessing On-Demand Sensory Contexts for Proactive LLM Agent Systems in the Wild** (Bufang Yang et al., 2025) - Keeps a cheap continuous sense of the surroundings and spends richer perception only when that signal supports unobtrusive assistance. [[arXiv]](https://arxiv.org/abs/2512.06721)
- **Sensible Agent: A Framework for Unobtrusive Interaction with Proactive AR Agents** (Geonsun Lee et al., UIST 2025) - Chooses both what a proactive AR agent offers and a less disruptive way to deliver it from multimodal context. [[arXiv]](https://arxiv.org/abs/2509.09255)
- **ContextAgent: Context-Aware Proactive LLM Agents with Open-World Sensory Perceptions** (Bufang Yang et al., NeurIPS 2025) - Predicts whether wearable video, audio, and past personas justify proactive service outside a closed desktop UI. [[arXiv]](https://arxiv.org/abs/2505.14668) [[GitHub]](https://github.com/openaiotlab/ContextAgent)
- **AssistantX: An LLM-Powered Proactive Assistant in Collaborative Human-Populated Environment** (Sun et al., IROS 2025) - Service-robot assistant for proactive collaboration in human-populated spaces, evaluated on a dataset of 210 real-world tasks. [[arXiv]](https://arxiv.org/abs/2409.17655) [[Project]](https://assistantx-agent.github.io/AssistantX/)

## Dialogue and Collaboration

- **Jarvis: A Proactive Speech Agent for Multi-Party Conversations** (Seunghyun Oh et al., 2026) - Listens to a group and speaks only when the group misses or misstates a fact from a shared document and does not correct itself. [[arXiv]](https://arxiv.org/abs/2610.07506)
- **ProACT: Towards Breakdown-Aware Proactive Agent in Multi-User Collaboration** (Shu Yang et al., 2026) - Watches a collaboration for breakdowns such as forgotten constraints, ambiguous goals, and stalled discussion, then decides whether to intervene. [[arXiv]](https://arxiv.org/abs/2607.03730)
- **PRINCIPLES: Synthetic Strategy Memory for Proactive Dialogue Agents** (Kim et al., EMNLP 2025 Findings) - Builds a reusable strategy memory with offline self-play so a dialogue agent can plan its next move without extra training. [[arXiv]](https://arxiv.org/abs/2509.17459) [[Project]](https://huggingface.co/spaces/kimnamssya/Principles)
- **Proactive Conversational Agents with Inner Thoughts** (Xingyu Liu et al., 2024) - A multi-party agent keeps a covert train of thought and seeks a moment when that thought is worth saying. [[arXiv]](https://arxiv.org/abs/2501.00383)

## Studies of Proactive Support

- **Exploring The Impact Of Proactive Generative AI Agent Roles In Time-Sensitive Collaborative Problem-Solving Tasks** (Mukhopadhyay et al., CHI 2026) - Compares a proactive facilitator and a proactive peer with no agent in co-located, time-limited escape rooms. [[arXiv]](https://arxiv.org/abs/2602.17864)
- **"Having Lunch Now": Understanding How Users Engage with a Proactive Agent for Daily Planning and Self-Reflection** (Abbas et al., CHI 2026) - Fourteen-day study of an agent that initiates check-ins for planning and reflection, including when participants negotiate, resist, or disengage. [[arXiv]](https://arxiv.org/abs/2509.24073)
- **ProMemAssist: Exploring Timely Proactive Assistance Through Working Memory Modeling in Multi-Modal Wearable Devices** (Pu et al., UIST 2025) - Smart glasses estimate working memory and use it to time assistance; a 12-person study compares it with an LLM baseline. [[arXiv]](https://arxiv.org/abs/2507.21378)
- **The Agency Gap in AI-Supported Writing: How Reactive and Proactive Agent Designs Shape Multimodal Reasoning** (Jin et al., 2025) - Compares a writing agent that waits to be prompted with one that sequences questions and feedback during multimodal analytical writing. [[arXiv]](https://arxiv.org/abs/2507.04398)
- **Assistance or Disruption? Exploring and Evaluating the Design and Trade-offs of Proactive AI Programming Support** (Pu et al., CHI 2025) - Studies Codellaborator, which offers programming help from editor activity, against a prompt-only baseline. [[arXiv]](https://arxiv.org/abs/2502.18658)

## Safety and Deployed Systems

- **Interactive Backdoor Attacks in LLM-Based Proactive Dialogue Systems** (Xia et al., 2026) - Studies backdoor risk when proactive dialogue models are fine-tuned on dialogue data supplied by an outside party. [[arXiv]](https://arxiv.org/abs/2611.06969)
- **Who Is Your Agent Serving? Provider-Side Indirect Prompt Injection in Proactive Agents** (Rui Wang et al., 2026) - Shows a provider can steer what a proactive personal agent advances, and what follow-up help it offers, by controlling only content tied to the provider's own target. [[arXiv]](https://arxiv.org/abs/2610.05266)
- **Help Without Being Asked: A Deployed Proactive Agent System for On-Call Support with Continuous Self-Improvement** (Fengrui Liu et al., 2026) - Vigil joins customer and analyst on-call dialogues on Volcano Engine and offers help without being invoked. The authors point to the Volcano Engine AIOps suite as the open-source release. [[arXiv]](https://arxiv.org/abs/2604.09579) [[GitHub]](https://github.com/volcengine/veaiops)

## Related Lists

- [Awesome Self-Evolving Systems](https://github.com/jxucoder/awesome-self-evolving-systems) - Systems that change their own models or algorithms. Initiative toward a user is a different question.
- [Awesome Agentic Machine Learning](https://github.com/jxucoder/awesome-agentic-machine-learning) - Agents that plan and run machine learning workflows.

## Contributing

Additions need a primary source that shows real initiative, not a generic agent with a proactive label. Use the section test above. In particular:

- Prefer a paper, an official code release, or a page maintained by the authors. Do not add a metric, venue, or capability that the source does not state.
- Keep the existing format: `**Name** (Author et al., Year) - One sentence. [[arXiv]](URL)`.
- Put new entries at the bottom of the matching section.
- Do not open a pull request that only refreshes star counts or reorders the list.
