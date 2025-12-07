---
layout: distill
title: Are LLM Agent Populations Really Emergent? A Comprehensive Perspective
description: Exploring emergent properties in populations of LLM agents through the lens of complex systems theory, examining social coordination, cooperation dynamics, and economic interactions in generative agent-based models.
date: 2026-04-27
future: true
htmlwidgets: true
hidden: true

# Mermaid diagrams
mermaid:
  enabled: true
  zoomable: true

# Anonymize when submitting
authors:
  - name: Anonymous

# must be the exact same name as your blogpost
bibliography: 2026-04-27-emergent-agents.bib

# Add a table of contents to your post.
toc:
  - name: Introduction
  - name: Generative LLM Agents
    subsections:
      - name: Agent Decision Making
      - name: Interaction Model
      - name: Emergent Social Behavior
  - name: What is Emergence?
    subsections:
      - name: Social Coordination & Conventions
      - name: Cooperation vs. Conflict
      - name: Social Influence & Dynamics
  - name: "AgentMarket: A Dynamic Network of Generative Agents"
    subsections:
      - name: Time-Varying Network Interaction Model
      - name: Simulation and Network Dynamics
      - name: Natural Language and Sentiment Analysis
  - name: Challenges and Future
    subsections:
      - name: Alignment
      - name: Multi-Agents are Complex Systems

---

## Introduction

Language agents powered by large language models (LLMs) have emerged within the long-standing field of agent design, which studies entities that use the environment to take actions autonomously, renewing classic ideas about perception, action, and rational choice <d-cite key="russell2013aima,helbing2012social"></d-cite>. Beyond the current hype, this intersection is mutually beneficial: LLMs' interacting and reasoning through natural language offers a new substrate for modeling classical agents, while agentic architectures impose structure that channels LLM capabilities <d-cite key="sumers2024cognitivearchitectureslanguageagents"></d-cite>. Generative agent-based modeling (GABM) is increasingly incorporating modules for reasoning, planning, and long-term memory, as exemplified by Park et al. <d-cite key="park2023"></d-cite>. As single agents have grown more sophisticated, attention has shifted to populations of LLM agents, where collective dynamics, coordination, division of labor, and convention formation can arise from local interactions rather than top-down design, potentially yielding behaviors not predictable from any one agent alone.

The rapid deployment of LLM-grounded autonomous agents across real applications heightens the need to understand these collective effects, both in machine–machine ecosystems and in their broader sociocultural interfaces <d-cite key="wang2024survey,brinkmann2023machine"></d-cite>. Recent multi-agent simulations show that generative agents can exhibit cooperation, competition, bargaining, and communication, sometimes negotiating norms and aligning on shared goals <d-cite key="ashery2025emergent,buscemi2025strategic,chen2025multi,tran2025multi,vallinder2024cultural"></d-cite>. Yet much observed coordination is scaffolded by design choices, and prevailing evaluation relies on narrow proxies (e.g., engagement or sentiment) as observed by Takata et al. <d-cite key="takata2025emergent"></d-cite>, overlooking the evolving processes through which cooperation, hierarchy, and alignment actually emerge over time. This raises a central question: If interacting LLM agents really are a complex system, which patterns spontaneously emerge in LLM populations, and under what conditions?

These concerns intersect with cooperative AI and alignment theory: as Dafoe et al. <d-cite key="dafoe2020open"></d-cite> note, advances in social and strategic competence create "differential capabilities" that can serve both pro-social and adversarial ends. In social-dilemma settings, rational local behavior can drive systems toward collectively suboptimal equilibria, especially if agents succeed via aggressive or manipulative tactics <d-cite key="pan2023machiavelli,anwar2024foundational"></d-cite>. Against this backdrop, we synthesize the literature, connect findings across social simulation (e.g., social simulacra and information spread), collaborative LLM environments (e.g., research labs and hospitals), and the most salient promise, emergent capabilities unattainable by single language agents.

To build new intuition, we outline observed emergent patterns in LLM agents and examine what populations of these models are actually capable of achieving. We then provide recommendations for studying this emergence, emphasizing that tools from complex systems are necessary to address the challenge of measuring these behaviors rigorously. Moreover, we present our brief contribution, which emerged in this exact same discussion. We modeled a dynamic network of agents, integrating long-term and working memory, reflection, and planning, while introducing mechanisms for merchant personality, sales management, inventory control, and production planning. To verify the emergent social structure, we model a time-varying interaction graph whose connectivity evolves with agents' preferences, specifically examining if it exhibits scale-free properties, characterized by a few dominant hubs among many sparsely connected nodes. The resulting economy exhibits human-like patterns, stable preferences, self-organizing network connectivity, and coherent production and trade strategies.

---

## Generative LLM Agents

While Language Models capture statistical relationships in human data, they lack inherent autonomy. Bridging this gap requires architectures that enable reasoning and task execution. Wang et al. <d-cite key="wang2024survey"></d-cite> identified four key modules for autonomous LLMs: profile, memory, planning, and action. Building on these concepts, Park et al. <d-cite key="park2023"></d-cite> introduced a standard for simulations where generative agents utilize cognitive architectures and environmental design to overcome coherence struggles, enabling them to plan, form relationships, and coordinate group activities.

### Agent Decision Making

The core architecture adopted by Park et al. <d-cite key="park2023"></d-cite>, formalized within the CoALA framework by Sumers et al. <d-cite key="sumers2024cognitivearchitectureslanguageagents"></d-cite>, treats the LLM as a central processor with a limited context window, which can be understood as the working-memory of the agent. To overcome this limitation, Park et al. <d-cite key="park2023"></d-cite> employed a Memory Stream that logs experiences into a database. A retrieval function dynamically populates working memory based on relevance, recency, and semantic similarity, while Reflection synthesizes these logs into high-level semantic memories. Temporal coherence is achieved through planning a hierarchical mechanism that translates semantic conclusions into action sequences, allowing the agent to dynamically balance daily schedules with reactions to spontaneous stimuli.

{% include figure.liquid path="assets/img/2026-04-27-emergent-agents/cognitive_architecture.png" class="img-fluid rounded z-depth-1" %}
<div class="caption">
    Cognitive architecture overview. Image from Sumers et al. <d-cite key="sumers2024cognitivearchitectureslanguageagents"></d-cite>.
</div>

### Interaction Model

Agents require a grounded existence to manifest behavior in the environment and with one another. In the "Smallville" simulation by Park et al. <d-cite key="park2023"></d-cite>, the environment is represented by a semantic tree (e.g., School → Classroom) translated into natural language. This allows agents to textually perceive and manipulate their surroundings. The system supports complex social dynamics and human-in-the-loop interactions, where users can directly alter environmental states or inject directives via an "inner voice" mechanism. This interaction model supports different scenarios, such as a hospital, similar to Smallville, where agents can be patients, nurses, and doctors treating diseases <d-cite key="li2025agenthospitalsimulacrumhospital"></d-cite>. However, the interaction model can also be defined by a set of coordinates, where agents receive information from their surroundings <d-cite key="takata2025emergent"></d-cite>, or by a network, such as our multi-agent marketplace, which models interactions as a time-varying directed probability network.

{% include figure.liquid path="assets/img/2026-04-27-emergent-agents/gabm_and_interactivemodel.png" class="img-fluid rounded z-depth-1" %}
<div class="caption">
    A complex system visualization of GABM and an Interaction Model. A schematic representation of the recursive coupling between agent and system states. Figure inspired by Lu et al. <d-cite key="LU2024283"></d-cite>; images adapted from Takata et al. and Park et al. <d-cite key="takata2025emergent,park2023"></d-cite>.
</div>

### Emergent Social Behavior

A critical finding of Park et al. <d-cite key="park2023"></d-cite> was the capacity for "emergent social behaviors," where complex dynamics arise without explicit scripting. This includes *information diffusion*, where news propagates through the population via organic conversations (e.g., a mayor election that spreads over Smallville), and *collaborative coordination*, where agents autonomously organize events (e.g., a party). These interactions demonstrate second-order effects, such as agents recruiting help or leveraging social networks to invite specific peers based on memory-encoded relationships.

Similarly, Williams et al. <d-cite key="williams2023epidemicmodelinggenerativeagents"></d-cite> utilized GABM to verify emergent capacity in simulations of public health scenarios. By modeling how individual agents react to disease vectors, the system generated macro-level trends that mirrored real-world data. Significantly, the agents' collective behavioral adaptations successfully 'flattened the curve,' while the simulation naturally gave rise to complex multi-wave and endemic infection patterns.

---

## What is Emergence?

The definition of emergence often depends heavily on the disciplinary lens applied. From a physics perspective, emergence is typically characterized by phase transitions where macroscopic properties spontaneously manifest within a system, such as a material acquiring magnetic properties as the temperature drops. This concept of spontaneous order is increasingly applied to the study of LLM agents. For instance, Ashery et al. <d-cite key="ashery2025emergent"></d-cite> investigate social conventions through the framework of complex systems, drawing parallels between the formation of norms and the "critical mass" phenomena observed in physical phase transitions. However, the majority of researchers in agentic literature define emergence more pragmatically as behavioral properties that appear in autonomous systems despite not being explicitly prompted. While these definitions differ in origin, they converge on the study of how properties arise in autonomous systems without direct hardcoding.

### Social Coordination & Conventions

Besides what Park et al. <d-cite key="park2023"></d-cite> called emergent coordination, more robust experiments in controlled settings were proposed to understand this phenomenon. To manage these dynamics in more complex environments, Ren et al. <d-cite key="ren2024emergencesocialnormsgenerative"></d-cite> propose the CRSEC architecture (Creation, Spreading, Evaluation, and Compliance). In their simulations, this architecture enabled the spontaneous emergence of robust social norms, specifically "no smoking indoors," "be quiet in public," and "tipping after meals", which effectively minimized social conflict without central enforcement.

Expanding on the mechanics of these conventions, Flint et al. <d-cite key="flint2025groupsizeeffectscollective"></d-cite> identify group size as a critical control parameter. Their findings reveal that collective bias is not merely an aggregation of individual preferences but a deeper phenomenon capable of amplification, induction, or reversal: interactions can amplify weak individual biases, induce new ones where none existed, or even reverse model-level preferences. Crucially, they observe non-linear effects where, above a critical population size, simulations converge to deterministic predictions, exposing the "basins of attraction" for competing equilibria.

In a more controlled environment, Ashery et al. <d-cite key="ashery2025emergent"></d-cite> propose an experiment to model using "Naming Games," where agents interact pairwise to negotiate a shared vocabulary. Simulations demonstrate that populations of LLM agents undergo a symmetry-breaking transition, evolving from a high-entropy state of distinct terms to a global norm via a "winner-take-all" trajectory. While theoretical models predict that any neutral option should have an equal probability of becoming the norm, LLM populations exhibit a phenomenon of Collective Bias. Even when individual agents appear unbiased in isolation, the collective dynamics of the group amplify specific latent preferences, resulting in non-neutral outcomes.

### Cooperation vs. Conflict

Emergence also manifests in strategic scenarios where agents must weigh self-interest against group benefit, a dynamic increasingly relevant in multi-agent systems <d-cite key="willis2025systemsllmagentscooperate"></d-cite>. While Willis et al. focus on population dynamics, the structural complexity of interactions is further elucidated by Du et al. <d-cite key="DU2025105439"></d-cite> in their analysis of triadic Prisoner's Dilemma games. Du et al. observed that the introduction of a third player significantly altered standard dyadic dynamics, as this third agent could stabilize cooperative relationships or destabilize defective ones, effectively mediating the group's state. Crucially, they found the emergence of cooperation to be highly sensitive to the 'K-index', Rapoport's measure of the relative incentive to cooperate versus defect, where higher values promoted sustained mutual cooperation even under minimal information conditions (for more details of this index see <d-cite key="rapoport1967note"></d-cite>).

Beyond immediate structural incentives, Vallinder and Hughes <d-cite key="vallinder2024cultural"></d-cite> extend the analysis to intergenerational dynamics, demonstrating that cooperative norms can emerge via cultural evolution rather than explicit pre-programming. In their study of the iterated Donor Game, they observed that sophisticated strategies of indirect reciprocity, where agents conditionally aid based on the reputation of others, emerged spontaneously to solve collective action problems. This emergence was characterized by the development of "second-order" reputation tracking and the utilization of costly punishment to police free-riders. However, they emphasize that this capacity is highly model-dependent; while populations of Claude 3.5 Sonnet agents successfully "bootstrapped" this cooperative infrastructure, other models like GPT-4o and Gemini 1.5 Flash converged toward mutual defection, highlighting that emergent cooperation relies on specific model capabilities for social learning across generations.

While these studies highlight how structural and evolutionary incentives drive cooperation, other research suggests that shared state information is equally critical for emergence in adversarial domains. In the context of Information Operations (IO), which are orchestrated campaigns to influence mass opinion on social media (e.g., election, fake news), Orlando et al. <d-cite key="orlando2025emergentcoordinatedbehaviorsnetworked"></d-cite> found that agents exhibited sophisticated strategic coordination without explicit planning. As operational regimes became more structured, IO networks spontaneously became denser and more clustered, with narratives converging toward semantic homogeneity. A key emergent finding was that simply providing agents with "Teammate Awareness" (mutual knowledge of allies) triggered coordination patterns, such as synchronized resharing and narrative alignment, that were nearly equivalent to those achieved through explicit, time-consuming deliberation.

### Social Influence & Dynamics

Finally, in scenarios requiring complex resource management, Takata et al. <d-cite key="takata2025emergent"></d-cite> explored the El Farol Bar problem, a classic game-theoretic scenario with no simple rational solution. They observed that LLM agents autonomously developed a "spontaneous motivation" to attend the bar, resulting in oscillatory attendance patterns that mirrored human behavior rather than perfect utility optimization. Notably, agents spontaneously employed hashtags (e.g. #collaboration) to signal intent and coordinate behavior. The study identified a consistent time lag between agent clustering and bar crowding, indicating that agents were forming a "collective mind" that anticipated group dynamics, balancing formal rationality with social motivations in a way standard game theory does not predict.

---

## AgentMarket: A Dynamic Network of Generative Agents

To extend the study of emergence into financial domains, we applied GABM within a dynamic digital marketplace. This environment facilitates peer-to-peer trading, supporting merchant leaderboards, distinct seller personas, and reinforcement-learning simulations. A core feature of our approach is inspired by complex system theory, by using a time-varying interaction graph, designed to explicitly model how social interactions restructure network connectivity over time. Building upon established cognitive architectures <d-cite key="park2023,sumers2024cognitivearchitectureslanguageagents"></d-cite>, we integrate long-term and working memory, reflection, and planning with novel domain-specific mechanisms: merchant personality, sales management, inventory control, and production planning. The resulting economy demonstrates human-like emergent patterns, including stable preferences, merchant clustering, and coherent strategies.

Building on this architecture, retrieved contexts fuel a reflection stage where agents synthesize observations through the lens of their unique personalities, shaping attributes such as risk tolerance and negotiation stance. Ultimately, these cognitive states dictate economic actions, as agents dynamically update production targets based on expected demand, driven by past interactions, and modulate their pricing strategies according to real-time inventory constraints.

{% include figure.liquid path="assets/img/2026-04-27-emergent-agents/cogntive.png" class="img-fluid rounded z-depth-1" %}
<div class="caption">
    Our Cognitive architecture overview, inspired by Park et al. <d-cite key="park2023"></d-cite> with inventory and production planning addition.
</div>

### Time-Varying Network Interaction Model

To allow different agents to interact and possibly trade with each other, we adopted a time-varying network interaction model inspired by complex networks and Markov chains (Watts and Strogatz <d-cite key="watts1998collective"></d-cite>). Let $$ N\in\mathbb{N} $$ be the number of agents and $$ t\in\mathbb{Z}_{\ge 0} $$ the discrete time index. Each agent $$ A_i\in\{1,\dots,N\} $$ produces a directional score for agent $$ A_j $$ via

$$
A_i:\ \mathbb{Z}_{\ge 0}\times\{1,\dots,N\}\to\mathbb{R},\qquad
s_{ij}(t)=A_i(t,j).
$$

The scores provided by the agents $$ S_t=\big[s_{ij}(t)\big]\in\mathbb{R}^{N\times N} $$, define the row-stochastic weight matrix by a row-wise softmax with temperature $$ \tau>0 $$:

$$
W_t = \operatorname{RowSoftmax}(S_t), \quad
w_{ij}(t)=\frac{\exp\!\big(s_{ij}(t)/\tau\big)}{\sum_{k=1}^N \exp\!\big(s_{ik}(t)/\tau\big)}.
$$

At each time step, agent $$ i $$ interacts with $$ j $$ with probability $$ P(A_i \rightarrow A_j)=w_{ij}(t) $$ or reflect by $$ P(A_i \rightarrow A_i)=1-w_{ii}(t) $$.

The interaction network is a time-varying matrix of probabilities $$ W_t $$ where $$ w_{ij}(t) $$ is the probability that agent $$ i $$ interacts with agent $$ j $$ at time $$ t $$.

{% include figure.liquid path="assets/img/2026-04-27-emergent-agents/agentmarket_graph.png" class="img-fluid rounded z-depth-1" %}
<div class="caption">
    Our interaction model, a time-varying weighted directed graph.
</div>

### Simulation and Network Dynamics

To investigate the emergence of social structure, we initialized the simulation with a uniform probability graph where all edge weights were identical. The simulation proceeds iteratively: at each step, an active agent selects a peer to interact with, after which the turn, and control of the interaction, passes to the receiver. To characterize the long-term behavior of these interactions, we conducted extensive simulations, tracking the structural evolution of the network over a horizon of 300 interactions.

As illustrated below, the network exhibits significant topological drift, quickly departing from its initial uniform state to fluctuate between distinct regimes of connectivity. Crucially, Maximum Likelihood Estimation of the node strength distribution reveals the emergence of a scale-free architecture over every scoring cycle. The observed exponent ($$ \alpha \approx 2.12 $$) signifies that the probability of a node having a certain strength decays relatively slowly, placing the system within the 'classic' range of natural complex networks like the Internet or metabolic pathways <d-cite key="PhysRevE.67.026112"></d-cite>. These networks follow a power law, characterized by a few dominant hubs among many sparsely connected nodes. This analysis captures the system's trajectory from randomness through intermediate phases of self-organization, demonstrating how connection probabilities evolve into a structured, hierarchical topology.

{% include figure.liquid path="assets/img/2026-04-27-emergent-agents/graphs.png" class="img-fluid rounded z-depth-1" %}
<div class="caption">
    Network topology evolution showing emergent scale-free properties and hierarchical structure.
</div>

Quantitative analysis of the network connectivity indicates a stabilization period following the initial configuration. The system's Global Efficiency rises sharply in the early cycles, peaking around cycle 5 before settling into a slightly lower steady state. This decline may connect with a gradual increase in the PageRank Gini coefficient, suggesting that as the network matures, influence becomes somewhat more concentrated, which correlates with a minor reduction in global integration. Meanwhile, Dyadic Reciprocity remains relatively high (>0.6) throughout the simulation, consistently exceeding levels expected in random or strictly hierarchical graphs. Together, these metrics characterize a system that evolves into a widely connected, feedback-rich structure with moderate centralization, rather than converging toward a pure star or random connectivity. Of course this is just preliminary result as serves as a motivation for more complex systems oriented approaches.

{% include figure.liquid path="assets/img/2026-04-27-emergent-agents/graph_metrics.png" class="img-fluid rounded z-depth-1" %}
<div class="caption">
    Plot with the Global Efficiency and Centrality (PageRank) over scoring cycles.
</div>

### Natural Language and Sentiment Analysis

Below, we present the final agreement phase. Here, the agents aren't just haggling; they are engaging in a culturally rich exchange. Note how Pema constructs a complex bundle, trading 'wild cliff honey' (80) against an 'underwater light' (85), and accurately computes the cash remainder, all while exchanging pleasantries like 'dhanyabad' and 'Que maravilha'. It is high-stakes trading, handled with grace.

{% include figure.liquid path="assets/img/2026-04-27-emergent-agents/chat_example.png" class="img-fluid rounded z-depth-1" %}
<div class="caption">
    Verbatim transcript of the negotiation settlement. Pema offers a split-payment trade (goods + currency), which Bianca accepts in the subsequent turn.
</div>

We also tried to identify which characteristics of agent interactions lead to a good trade. In order to verify this we applied LLM as judge to give sentiment analysis scores, this method was chosen over sentiment-BERT, since most of the models cannot deal with large corpus of data, such as a whole interaction between the agents. We observe a positive Spearman correlation between trade value and positive score for the conversation ($$ r=0.33, p<0.001 $$) and a slightly negative correlation for negative scores ($$ r=-0.12, p<0.001 $$).

{% include figure.liquid path="assets/img/2026-04-27-emergent-agents/sentiment_analysis.png" class="img-fluid rounded z-depth-1" %}
<div class="caption">
    The scatter plot in blue shows the positive correlation between the log trade value, to facilitate visualization, and positive sentiment score. In the red scatter plot, the negative correlation between the log trade value and negative sentiment score.
</div>

Ultimately, we wanted to provide an example and further motivation to treat multi-agents as complex systems by changing the usual interaction model for a time-varying network defined by the agent preference over a marketplace environment. These simulations reveal a human-like marketplace where the emergence of distinct seller preferences and natural clusters that might mirror real-world economic configurations. However, more importantly, we were able to investigate how the social layer might relate to the economic one and provided an analysis framework based on complex systems tools in networks.

---

## Challenges and Future

### Alignment

On the positive side, emergent coordination among AI agents can be harnessed for pro-social outcomes. For example, a well-designed population of healthcare assistant agents could divide labor and share information to diagnose patients more effectively than any single agent, utilizing agent-to-agent communication like negotiation and debate to coordinate effectively <d-cite key="carichon2025comingcrisismultiagentmisalignment"></d-cite>. In our AgentMarket, agents eventually stabilized their market and improved efficiency, analogously, multiple AI agents managing an energy grid or traffic system might emergently reduce waste or prevent overloads through their local interactions. These are cases where we want emergence: the system-level outcome is better than a centralized or solo approach, and ideally aligned with our goals (healthier patients, efficient markets, etc.).

However, emergent behaviors can also pose alignment risks. As mentioned earlier, agents with advanced social skills have differential capabilities which can lead to power asymmetries and over-reliance on confident or dominant agents <d-cite key="carichon2025comingcrisismultiagentmisalignment"></d-cite>; they might collude in ways that are harmful, or develop their own objectives that diverge from what we intended. A concrete concern is emergent deception or power-seeking in multi-agent systems. If one agent learns it can achieve its goal by manipulating another, such as hiding or spreading false information to prevent others from benefiting freely <d-cite key="carichon2025comingcrisismultiagentmisalignment"></d-cite>, and this behavior spreads or is copied by others, the group could develop a norm of deception that undermines overall performance and violates human norms. The Machiavelli benchmark study showed that without constraints, agents often choose Machiavellian strategies to win <d-cite key="pan2023rewardsjustifymeansmeasuring"></d-cite>, a risk exacerbated in groups where exploitative individuals can manipulate group dynamics for personal gain. In a multi-agent context, if competitive pressure pushes even a few agents to be dishonest for gain, others may follow suit to avoid exploitation, leading to an undesirable equilibrium of low trust and unethical behavior. This is analogous to how unchecked competition in markets can lead to a "race to the bottom" or how social media algorithms all optimize for engagement, possibly leading to the spread of sensational or false content as an emergent outcome.

### Multi-Agents are Complex Systems

We hope this discussion has demonstrated that interacting LLM agents are effectively complex systems, capable of exhibiting distinct emergent properties. However, a major open challenge remains: the rigorous quantification of this emergence. While recent research attempts to establish more reliable metrics, prevailing evaluations often rely on "narrow proxies" such as task success rates or sentiment analysis. While these indicators are informative from a natural language standpoint, they provide insufficient resolution, highly susceptible to sensitive changes in prompt and model characteristics, when modeling the system's global properties as also highlighted by Lu et al. <d-cite key="LU2024283"></d-cite>. Crucially, such metrics indicate that coordination has occurred, but fail to explain the causal mechanics of how macro-level phenomena, such as the observed emergent social behavior, decouple from micro-level agent states. To truly understand multi-agent intelligence, the field must transcend behavioral observation and adopt the quantitative rigor of complex systems theory as we tried to illustrate with Ashery et al. <d-cite key="ashery2025emergent"></d-cite> and our AgentMarket example.

As a recommendation to the community, to evaluate emergence from a more structured quantifiable way, using complex system literature and information-theoretic standpoint, such as frameworks such as those proposed by Rosas et al. <d-cite key="rosas_pedro_emergence_2020"></d-cite>. This approach posits that emergence is not merely a qualitative description but a quantifiable state of synergistic information, where the predictive power of the collective system exceeds the sum of information contained in its individual components.
