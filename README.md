<a href="https://polargrid.ai"><img src="assets/hero.svg" width="100%" alt="Sev Geraskin. AI has to answer as fast as a person would. So the computer has to sit near the person. A dark world map of PolarGrid's sites as of October 2026: eight live sites in North America (Seattle, San Jose, Los Angeles, Dallas, Miami, Ashburn, New York and Montreal) glow pink, thirty-five planned sites on five continents are dashed rings, and requests from North American cities fly to the nearest live site."></a>

**Co-founder and VP Engineering, [PolarGrid](https://polargrid.ai)** · **President, [Economy of Wisdom Foundation](https://economyofwisdom.org)** · Vancouver, BC

Real-time AI inference at the edge. Distributed systems that scale. Frameworks that ask whether technology serves people.

## PolarGrid: served from the site nearest every user

One endpoint, global inference delivery. Each request is served from the site nearest the user, so time to first token stays low in every region.

<img src="assets/near.svg" width="100%" alt="Before the first word, a race slowed down four times. People: 0 to 300 milliseconds, the median in ten languages. Nearby, one PolarGrid node: 364 milliseconds. Centralized, three cloud models: 0.8 to over 1.6 seconds. Sources: Stivers et al., PNAS 2009; polargrid.ai, February 2026.">

**Why near matters.** In all ten languages studied, the median gap before people answer each other is between 0 and 300 milliseconds. Past 300 milliseconds, listeners begin anticipating a hedged response. Our voice pipeline on one nearby node has a median of 364 milliseconds from audio in to audio out; a chain of centralized models takes 0.8 to over 1.6 seconds.

<img src="assets/failover.svg" width="100%" alt="Resilient by design, a drill on a loop. North America as dots with PolarGrid's eight live sites and lines from cities to their nearest site. One site goes dark, its lines swing to the next nearest site, and the status reads: one site down, its traffic moved to the next nearest, endpoint up. Then all sites are up again.">

**If a site goes down, its traffic moves to the next nearest site and the endpoint stays up.** When traffic surges in one region, nearby sites take the overflow.

<details>
<summary><b>How it works, for engineers</b></summary>
<br>

| Layer | What it does |
|---|---|
| Inference | OpenAI-compatible endpoints, autoscaling replicas, and request routing to the nearest healthy site. |
| Orchestration | Scheduling, rollouts, and failover across sites, so a deployment is described once and runs everywhere. |
| Compute | Dedicated GPU capacity, tuned runtimes, and storage paths sized for loading large checkpoints fast. |
| Hardware | Partner data centers with power, cooling, and networking we specify, accept, and operate with the site teams. |

- **Local hot path.** Anything in the hot path is local to the node. Anything that can tolerate seconds or minutes of staleness can be centralized. [Running inference across multiple colos without a central brain](https://www.polargrid.ai/blog/running-inference-across-multiple-colos-without-a-central-brain)
- **Routing.** The SDK probes candidate nodes, caches the result for five minutes, and falls back to the next-best node when a request fails. [Building a regionally-aware model router](https://www.polargrid.ai/blog/building-a-regionally-aware-model-router)
- **Voice on one node.** Speech-to-text, the language model and text-to-speech run on the same physical GPU node, so the step between stages is a memory copy. [Anatomy of a sub-400ms STT→LLM→TTS pipeline](https://www.polargrid.ai/blog/anatomy-of-a-sub-400ms-stt-llm-tts-pipeline)
- **Observability.** Per-request telemetry at every gateway, synthetic benchmarks, and model cards built from dated benchmark files. [Our inference observability stack](https://www.polargrid.ai/blog/our-inference-observability-stack)

</details>

## Economy of Wisdom Foundation: every organization moves human needs

<img src="assets/quadrant.svg" width="100%" alt="Every organization moves human needs. We measure which way. A quadrant: Transmuter filters deprivation and amplifies fulfillment (+F +A); Absorber +F −A; Magnifier −F +A; Extractor −F −A; the Conduit sits at the centre. Nine published placements drift in: UBC, Ai2 (OLMo) and Quebec AI policy as Transmuters; Bill C-34 and Telus data centres as Absorbers; DeepSeek and Ontario AI policy as Magnifiers; Bill C-22 as an Extractor; US tariffs on Canadians on the line. Readings of the public record, not audits.">

**We measure which way.** Transmutarianism is a published framework for scoring what an organization, project or AI system does to the people it touches: the hardship it absorbs, and the fulfillment it passes on. Each dot is a field note's published reading of the public record.

<img src="assets/voices.svg" width="100%" alt="If AI could learn one thing from human beings to make the world better, what should it learn? Fifty-one figures, one per person interviewed; twenty-two light up red. 43%: 22 of 51 people named compassion, care or kindness as their first answer. The same category was absent from the 81,000-person survey on what people want from AI.">

**Whose values train AI?** In March 2026, 51 people in Vancouver's Downtown Eastside were interviewed in person. Asked what AI should learn from human beings, 22 of them named compassion, care or kindness first. [Read the paper](https://doi.org/10.5281/zenodo.19582415).

<img src="assets/world.svg" width="100%" alt="Where the world's compute sits. A dot map of the world shaded by country income group, with low-income countries in red. High-income countries hold 77% of global data-centre capacity; low-income countries hold under 0.1%. Source: World Bank, via economyofwisdom.org; income groups from Natural Earth.">

**Where the world's compute sits.** Low-income countries hold under 0.1% of global data-centre capacity, against 77% for high-income countries (World Bank). [Field note](https://economyofwisdom.org/blog/2026-08-02-open-weight-labs/)

<img src="assets/ccc.svg" width="100%" alt="A modern commons based on the public library model, open to anyone who walks in. Designed and costed, not yet sited. A building in section: the compute room with 19 eight-GPU nodes in four racks, glazed to the street, with people walking in; the commons and cafeteria with 48 public AI terminals; rest and exercise; twelve homes; a planted roof. No membership, no purchase, no appointment, no ID.">

**A Compute Community Centre** is a modern commons based on the public library model, open to anyone who walks in. It is designed and costed, and not yet sited. [See the design](https://economyofwisdom.org/compute-community-centre/)

<details>
<summary><b>For researchers</b></summary>
<br>

- **Transmutarianism**, a moral accounting framework for measuring deprivation and fulfillment flows through agent networks: `M = τF + A`. DOI [10.5281/zenodo.18809258](https://doi.org/10.5281/zenodo.18809258)
- **Whose Values Train AI? Evidence from 51 interviews in Vancouver's Downtown Eastside.** DOI [10.5281/zenodo.19582415](https://doi.org/10.5281/zenodo.19582415)
- **Synthetic Voices**: real speakers produce hesitation and filler at 49.4 markers per 1,000 words; the four language models tested produce between 0.25 and 6.9. DOI [10.5281/zenodo.20262752](https://doi.org/10.5281/zenodo.20262752)
- **17 field notes** that score named institutions on one reproducible map: [economyofwisdom.org/blog](https://economyofwisdom.org/blog/)

</details>

## Thinking

I believe compute infrastructure is a question of cognitive sovereignty. Who controls the inference layer shapes who benefits from AI.

## Work that mattered

- Scaled distributed data services **100×** at Mastercard while cutting cloud costs **75%**, with pipelines that unlocked multimillion-dollar opportunities
- Built PolarGrid's infrastructure stack from scratch: two-tier Kubernetes, GPU passthrough, MetalLB, bare-metal Supermicro
- Mentored four AI startups through Scale AI's Zen Launchpad Cohort 2
- Published **Transmutarianism** (DOI [10.5281/zenodo.18809258](https://doi.org/10.5281/zenodo.18809258)), a moral accounting framework for measuring deprivation and fulfillment flows through agent networks
- Developed PITC (Physical-Information Theory of Consciousness), distinguishing crystallized intelligence from fluid consciousness in AI-integrated substrates

## Technical depth

```
Infrastructure     Kubernetes (MicroK8s, Kata containers) · MetalLB · bare metal GPU clusters
AI/ML              Triton Inference Server · Whisper · Qwen · LLaMA · Nemotron · Kokoro TTS · NVIDIA Blackwell
Cloud              AWS (Solutions Architect, Security certified) · multi-region distributed systems
Languages          Python · Go · TypeScript · Bash
Domains            Voice AI · agent orchestration · AI alignment · real-time inference · LLM serving
```

BCIT · AI Alignment · AWS Solutions Architect · AWS Security · Generative AI · PMP

## Connect

[LinkedIn](https://linkedin.com/in/past5) · [PolarGrid](https://polargrid.ai) · [Economy of Wisdom](https://economyofwisdom.org) · [Past 5 Solutions](https://past5.com)

*The real measure of any system is whether it transforms deprivation into fulfillment for the people and communities it serves.*

<sub>Graphics drawn for this profile from public PolarGrid and Economy of Wisdom pages; sources in [assets/SOURCES.md](assets/SOURCES.md).</sub>
