---
layout: default
title: "每日速递：2026-05-07 (EN)"
date: 2026-05-07
lang: en
---

> From 35 items, 14 important content pieces were selected

---

1. [NVIDIA and OpenAI Launch Open-Source MRC for Faster RDMA Multi-Path AI Networking](#item-1) ⭐️ 8.0/10
2. [Xiaomi releases OmniVoice: minimal bidirectional Transformer for 646-language voice-cloning TTS](#item-2) ⭐️ 8.0/10
3. [sglang v0.5.11 modernizes CUDA/Torch and defaults Speculative Decoding V2](#item-3) ⭐️ 7.0/10
4. [Library of Congress Recommends SQLite-Based Storage for Long-Term Preservation](#item-4) ⭐️ 7.0/10
5. [noyb challenges LinkedIn’s withholding of profile visitor lists](#item-5) ⭐️ 7.0/10
6. [Google Cloud Fraud Defense as the next reCAPTCHA evolution](#item-6) ⭐️ 7.0/10
7. [Anthropic and SpaceX expand Claude Code/API rate limits via Colossus 1 compute](#item-7) ⭐️ 7.0/10
8. [UK FCA opens competition probe into PayPal, Mastercard and Visa wallet contracts](#item-8) ⭐️ 7.0/10
9. [Valve releases Creative Commons CAD/STL files for Steam Controller accessories](#item-9) ⭐️ 6.0/10
10. [When “Appearing Productive” Rewards Inflated Work and Weakened Judgment](#item-10) ⭐️ 6.0/10
11. [Vibe coding and agentic engineering are starting to converge](#item-11) ⭐️ 6.0/10
12. [Permacomputing Principles: Ethical, resilient computing guidance](#item-12) ⭐️ 6.0/10
13. [datasette-referrer-policy 0.1 fixes OSM tiles by adjusting CAPTCHA and Referrer-Policy](#item-13) ⭐️ 6.0/10
14. [Apple R&D hits 10.3% of revenue as it accelerates AI hardware strategy](#item-14) ⭐️ 6.0/10

---

<a id="item-1"></a>
## [NVIDIA and OpenAI Launch Open-Source MRC for Faster RDMA Multi-Path AI Networking](https://blogs.nvidia.com/blog/spectrum-x-ethernet-mrc/) ⭐️ 8.0/10

NVIDIA, OpenAI, and Microsoft jointly released and open-sourced the MRC (Multi-Path Reliable Connection) protocol, a RDMA networking approach designed for AI supercomputing clusters. The protocol uses packet “spraying” across multiple paths for concurrent transfer and provides microsecond-scale failure rerouting to reduce GPU idle time and improve throughput and stability. AI training clusters are often limited by network congestion and fault handling, which can directly translate into idle GPUs and lower overall training efficiency. By standardizing and deploying MRC across major platforms, the ecosystem can improve scalability and reliability for large-scale AI workloads while reducing vendor fragmentation. MRC is positioned as a single RDMA connection that can distribute traffic across multiple network paths, combining throughput/load balancing with fast rerouting. The announcement also ties deployment to NVIDIA Spectrum-X (including Blackwell) and running clusters such as Microsoft Fairwater and Oracle OCI Abilene, with references to supporting model training workloads.

telegram · zaihuapd · May 6, 14:39

**Background**: RDMA is a networking technology used in data centers to move data with low latency and high throughput, which is important for GPU-based AI training. Multi-path transport aims to use multiple network paths concurrently to improve utilization and resilience, but it must also handle ordering, congestion, and failures carefully. NVIDIA Spectrum-X is an AI-native Ethernet fabric that supports RDMA-related routing and load balancing features, and MRC is presented as an open, standardized way to bring multi-path reliability into such fabrics.

<details><summary>References</summary>
<ul>
<li><a href="https://blogs.nvidia.com/blog/spectrum-x-ethernet-mrc/">NVIDIA Spectrum-X — the Open, AI-Native Ethernet Fabric — Sets the Standard for Gigascale AI, Now With MRC | NVIDIA Blog</a></li>
<li><a href="https://blogs.nvidia.cn/blog/spectrum-x-ethernet-mrc/">NVIDIA Spectrum-X — 开放的 AI 原生以太网架构 — 全面支持 MRC，为超大规模 AI 设定新标准 | NVIDIA 英伟达博客</a></li>
<li><a href="https://www.usenix.org/conference/nsdi18/presentation/lu">Multi-Path Transport for RDMA in Datacenters | USENIX</a></li>

</ul>
</details>

**Tags**: `#AI 超算网络`, `#RDMA`, `#多路径传输`, `#OCP 标准`, `#NVIDIA Spectrum-X`

---

<a id="item-2"></a>
## [Xiaomi releases OmniVoice: minimal bidirectional Transformer for 646-language voice-cloning TTS](https://mp.weixin.qq.com/s/TCS_Sd10g_rvf1cszw673A) ⭐️ 8.0/10

Xiaomi open-sourced OmniVoice, a massively multilingual voice-cloning TTS model that claims to use a minimal bidirectional Transformer architecture. The project reports training on 580,000 hours across 646 languages (built from 50 open datasets) and provides training/inference code plus model weights. If the reported results hold, OmniVoice could significantly lower the barrier to building high-quality cross-language voice-cloning TTS systems by offering a single model covering hundreds of languages. It may also influence how future TTS architectures balance simplicity, training efficiency, and intelligibility. The content states OmniVoice uses full-token random masking and “LLM pretraining parameters” to improve efficiency and intelligibility, with claimed training speed of 100,000 hours/day and PyTorch inference at 40× real time. It also claims better synthesis quality than mainstream comparable models, and supports cross-language cloning, custom voice design, noisy-audio adaptation, and pronunciation correction.

telegram · zaihuapd · May 7, 10:06

**Background**: TTS (text-to-speech) converts text into speech, while voice cloning aims to synthesize speech in a target speaker’s voice. Multilingual voice cloning extends this to many languages, typically requiring models that can generalize across language and speaker variations. Transformer-based architectures are common in modern sequence modeling, and “non-autoregressive” or simplified designs are often pursued to improve inference speed.

<details><summary>References</summary>
<ul>
<li><a href="https://www.ithome.com/0/947/354.htm">小米开源 OmniVoice 多语言语音克隆 TTS，号称一个模型搞定 600 余种...</a></li>
<li><a href="https://github.com/k2-fsa/OmniVoice/">GitHub - k2-fsa/OmniVoice: High-Quality Voice Cloning TTS for ...</a></li>

</ul>
</details>

**Tags**: `#语音克隆`, `#TTS`, `#多语言语音`, `#Transformer`, `#开源模型`

---

<a id="item-3"></a>
## [sglang v0.5.11 modernizes CUDA/Torch and defaults Speculative Decoding V2](https://github.com/sgl-project/sglang/releases/tag/v0.5.11) ⭐️ 7.0/10

sglang v0.5.11 updates the default build/runtime stack to CUDA 13.0 and upgrades PyTorch from 2.9 to 2.11 across SGLang, sgl-kernel, and Docker images. It also makes Speculative Decoding V2 the default (with overlap scheduling to reduce CPU overhead), improves prefix caching for prefill/decode disaggregated decoding via a decode radix cache, and adds cookbook recipes for many new models. These changes target the two biggest levers in LLM serving performance: faster kernels/build compatibility (CUDA 13 + Torch 2.11) and lower per-step or end-to-end latency through better decoding strategies and caching under disaggregated deployments. Practitioners deploying high-throughput or long-context workloads—especially on heterogeneous GPU setups—should see more predictable latency and easier model onboarding. Speculative Decoding V2 is now the default and uses overlap scheduling to hide CPU overhead specifically for EAGLE/MTP/DFLASH speculative decoding paths. For disaggregated prefill/decode, sglang adds decode-side prefix caching using a radix cache to recover hit rates and reduce TTFT for long shared prefixes.

github · Kangyan-Zhou · May 5, 21:28

**Background**: SGLang is a high-performance inference/serving framework for large language models and multimodal models, emphasizing low latency and high throughput. It includes mechanisms like RadixAttention for prefix caching and supports speculative decoding and prefill/decode disaggregation, where prefill and decode run in different workers. Speculative decoding uses a smaller draft model to propose tokens and a larger model to verify them, and V2 adds an overlap scheduling approach to reduce CPU-side overhead.

<details><summary>References</summary>
<ul>
<li><a href="https://github.com/sgl-project/sglang/releases">Releases · sgl-project/sglang</a></li>
<li><a href="https://docs.sglang.io/advanced_features/speculative_decoding.html">Speculative Decoding — SGLang</a></li>
<li><a href="https://sgl-project.github.io/">SGLang Documentation — SGLang</a></li>

</ul>
</details>

**Tags**: `#LLM Inference`, `#Speculative Decoding`, `#GPU/CUDA`, `#Systems Optimization`, `#Model Serving`

---

<a id="item-4"></a>
## [Library of Congress Recommends SQLite-Based Storage for Long-Term Preservation](https://sqlite.org/locrsf.html) ⭐️ 7.0/10

The Library of Congress has published guidance listing a SQLite-based storage format as a “Recommended Storage Format” for long-term preservation of datasets. The recommendation has prompted discussion about whether SQLite’s durability and operational characteristics are appropriate for archival use, and what lightweight alternatives might look like. An authoritative institution endorsing a specific storage format can materially influence preservation practices and tooling across archives, researchers, and data stewards. If widely adopted, it could standardize how datasets are packaged for future access while also shifting risk considerations to SQLite-specific assumptions and configurations. The LoC guidance frames SQLite as a recommended format for long-term preservation, and the SQLite project describes it as a single-file database format suitable as an “Application File Format.” Community comments also highlight tradeoffs such as operational risk, the importance of correct usage patterns (e.g., single-writer/multiple-reader), and concerns about how easy it is to treat a database file like a generic file that can be copied around.

hackernews · whatisabcdefgh · May 6, 21:58 · [Discussion](https://news.ycombinator.com/item?id=48042434)

**Background**: A “Recommended Storage Format” is guidance intended to help repositories choose formats that remain usable over long periods. SQLite is an embedded, lightweight database that stores data in a single file and supports transactions and ACID guarantees. The discussion in this news item also references technical protection mechanisms (such as encryption) that can affect whether preserved content remains accessible to a trusted repository.

<details><summary>References</summary>
<ul>
<li><a href="https://sqlite.org/locrsf.html">LoC Recommended Storage Format</a></li>
<li><a href="https://sqlite.org/onefile.html">SQLite: Single File Database</a></li>
<li><a href="https://en.wikipedia.org/wiki/SQLite">SQLite - Wikipedia</a></li>

</ul>
</details>

**Discussion**: Overall sentiment is positive toward SQLite’s practicality, with commenters noting it can be reliable when used with appropriate settings and patterns. However, some raise governance and operational concerns, such as firms banning SQLite because it can become a critical “file-like” component that is easy to copy and may contain sensitive data. Others discuss lightweight approaches (e.g., small WebAssembly readers and zstd-compressed variants) as potential complements or alternatives.

**Tags**: `#SQLite`, `#Data Preservation`, `#Archival Formats`, `#Systems Engineering`, `#WebAssembly`

---

<a id="item-5"></a>
## [noyb challenges LinkedIn’s withholding of profile visitor lists](https://www.theregister.com/offbeat/2026/05/05/noyb-cries-foul-on-linkedin-withholding-profile-visitor-data/5225338) ⭐️ 7.0/10

NOYB has challenged LinkedIn’s handling of “who’s viewed your profile” data, arguing that LinkedIn improperly withholds profile visitor lists despite privacy-related justifications. The Register reports that for LinkedIn Premium users the visitor list can show names, job titles, and employers for up to 365 days, unless the visitor has toggled visibility off for privacy reasons. This dispute is significant because it targets how a major social network applies data protection and third-party rights when responding to access requests for tracking-related information. If NOYB’s complaint succeeds, it could affect how LinkedIn and similar platforms disclose or restrict profile-visitor data and how they justify paywalled access. According to the reporting, LinkedIn’s “who’s viewed your profile” function includes an option to control whether others can see that you viewed their profile, and Premium users receive fuller details than non-paying users. NOYB argues LinkedIn’s refusal conflicts with its privacy rationale because the same information is allegedly shared with paying Premium customers.

hackernews · robin_reala · May 7, 11:08 · [Discussion](https://news.ycombinator.com/item?id=48047970)

**Background**: “Who’s viewed your profile” is a LinkedIn feature that reports profile visitors, with visibility controlled via profile viewing options in Settings & Privacy. The underlying legal context is the GDPR, which includes rights related to access and disclosure of personal data. NOYB’s complaint frames the issue as a potential GDPR access/disclosure problem tied to platform tracking and paywalled access.

<details><summary>References</summary>
<ul>
<li><a href="https://www.theregister.com/offbeat/2026/05/05/noyb-cries-foul-on-linkedin-withholding-profile-visitor-data/5225338">Noyb cries foul on LinkedIn withholding profile visitor data</a></li>
<li><a href="https://www.linkedin.com/help/linkedin/answer/a568195">Who's viewed your profile visibility settings | LinkedIn Help</a></li>

</ul>
</details>

**Discussion**: Community reactions are broadly supportive of NOYB’s privacy stance, with commenters praising privacy-focused non-profits for challenging tech companies. Some skepticism appears in the form of debate about how much the withheld data would practically enable misuse, and one commenter disputes part of LinkedIn’s spokesperson statement by pointing to a screenshot. Others note that similar “who saw you” visibility models exist in dating apps, though they argue the risk profile may differ.

**Tags**: `#privacy`, `#data protection`, `#platform tracking`, `#legal/regulatory`, `#social networks`

---

<a id="item-6"></a>
## [Google Cloud Fraud Defense as the next reCAPTCHA evolution](https://cloud.google.com/blog/products/identity-security/introducing-google-cloud-fraud-defense-the-next-evolution-of-recaptcha/) ⭐️ 7.0/10

Google Cloud announced “Google Cloud Fraud Defense,” positioned as the next evolution of reCAPTCHA for improving fraud detection and mitigation across online interactions. The product is described as observing telemetry across web, mobile, and agentic surfaces, then correlating signals from registration/login through cart additions to final payment. This matters because it signals a shift from classic CAPTCHA-style challenges toward broader identity and fraud risk scoring that spans the full user journey. If adopted, it could affect how websites authenticate humans vs. automated agents and how privacy-sensitive signals are handled during registration, checkout, and other high-risk flows. The “how it works” description emphasizes correlating signals across multiple stages (registration/login, cart additions, payment) and across multiple surfaces (web, mobile, and MCP/A2A/agentic surfaces). Community comments also highlight potential client-side/browser requirements and concerns that challenges may rely on mobile device capabilities (e.g., QR-code scanning) that could introduce privacy and security risks.

hackernews · unforgivenpasta · May 6, 17:59 · [Discussion](https://news.ycombinator.com/item?id=48039362)

**Background**: reCAPTCHA is a CAPTCHA system used to distinguish humans from automated bots by presenting challenges or using risk signals. Fraud detection in identity and web security typically combines behavioral signals across sessions and transaction steps to reduce account takeover and payment fraud. The announcement frames Fraud Defense as an evolution that extends beyond simple web challenges into a more end-to-end, telemetry-driven approach.

<details><summary>References</summary>
<ul>
<li><a href="https://cloud.google.com/security/products/fraud-defense">Google Cloud Fraud Defense - The evolution of reCAPTCHA.</a></li>
<li><a href="https://allheadline.com/introducing-google-cloud-fraud-defense-the-next-evolution-of-recaptcha/">Introducing Google Cloud Fraud Defense , the next evolution of...</a></li>

</ul>
</details>

**Discussion**: The Hacker News discussion is largely skeptical, focusing on practical friction and privacy implications. Commenters question whether the solution effectively requires modern mobile devices (and possibly specific browser/client capabilities) and worry it could enable de-anonymization via mobile identifiers. Others criticize the proposed challenge design (e.g., QR-code scanning) as potentially risky if misused or compromised.

**Tags**: `#fraud-detection`, `#identity-security`, `#CAPTCHA`, `#web-application-security`, `#privacy`

---

<a id="item-7"></a>
## [Anthropic and SpaceX expand Claude Code/API rate limits via Colossus 1 compute](https://www.anthropic.com/news/higher-limits-spacex) ⭐️ 7.0/10

Anthropic said it has reached a compute partnership with SpaceX to use the full capacity of the Colossus 1 data center, adding over 300 MW of capacity within a month and more than 220,000 NVIDIA GPUs. Starting immediately, Anthropic increased Claude Code rate limits (doubling the 5-hour rate limit for paid plans and removing peak-time limits for Pro/Max) and significantly raised Claude Opus API rate limits. This is significant because it directly increases the available inference capacity for Anthropic’s key products, reducing friction caused by rate limits for both subscription users and API developers. The scale of the added GPU capacity also signals stronger infrastructure commitments that could affect how quickly new features and workloads can be supported across the Claude ecosystem. Anthropic’s announcement ties the limit increases to access to Colossus 1 compute, with “over 300 MW” and “over 220,000 NVIDIA GPUs” cited as the capacity basis. The specific changes include doubling Claude Code’s 5-hour rate limit for paid plans, removing peak-time limits for Pro/Max users, and raising Claude Opus API rate limits.

telegram · zaihuapd · May 6, 16:35

**Background**: Claude Code and Claude API are Anthropic’s main ways for users to access Claude capabilities, with different quota and throttling mechanisms. “Rate limits” are usage caps that can restrict requests or usage over a time window to manage shared compute resources. Colossus 1 is a large AI data center compute resource; securing additional capacity from a major infrastructure provider is one way to increase throughput and reduce throttling.

<details><summary>References</summary>
<ul>
<li><a href="https://techorange.com/2026/05/07/anthropic-spacex-ai/">化敵為友的百萬瓦級交易：拆解 Anthropic 承租 SpaceX Colossus 1 背...</a></li>
<li><a href="https://yingtu.ai/zh/blog/claude-code-rate-limit-fix">Claude Code使用限制完全指南：2026年订阅计划、速率限制与429错误解...</a></li>

</ul>
</details>

**Tags**: `#LLM推理算力`, `#Anthropic`, `#Claude API`, `#GPU集群`, `#算力合作`

---

<a id="item-8"></a>
## [UK FCA opens competition probe into PayPal, Mastercard and Visa wallet contracts](https://www.fca.org.uk/news/press-releases/competition-act-1998-investigations) ⭐️ 7.0/10

The UK Financial Conduct Authority (FCA) has opened a competition-law investigation into PayPal, Mastercard, and Visa related to digital wallet contract terms, with a particular focus on PayPal. The companies say they are cooperating, and the FCA has not yet reached a conclusion on whether competition law was breached. This matters because digital wallets are rapidly gaining share in the UK, and contract terms can materially affect market access and competitive dynamics. The investigation could lead to changes in how wallet providers structure agreements, impacting payment networks and merchants that rely on them. The FCA’s scope centers on contract terms, especially those tied to PayPal, rather than on a single product feature. The outcome is not yet determined, so any compliance or contractual changes by the firms would depend on the FCA’s eventual findings.

telegram · zaihuapd · May 7, 14:46

**Background**: Digital wallets are payment tools that let users transact electronically, and their growing adoption can reshape competition among payment providers. The FCA previously urged stronger competition among digital wallet providers to encourage innovation and market entry. In parallel, the UK’s CMA has also opened an antitrust investigation into the mobile ecosystems of Apple and Google.

<details><summary>References</summary>
<ul>
<li><a href="https://cn.wsj.com/articles/英国反垄断监管机构调查苹果、谷歌移动生态系统影响力-11623799811">英 国 反 垄 断 监 管 机 构 调 查 苹果、谷歌移动生态系统影响力 - WSJ</a></li>

</ul>
</details>

**Tags**: `#监管合规`, `#反垄断/反竞争`, `#数字钱包`, `#支付网络`, `#FCA`

---

<a id="item-9"></a>
## [Valve releases Creative Commons CAD/STL files for Steam Controller accessories](https://www.digitalfoundry.net/news/2026/05/valve-releases-steam-controller-cad-files-under-creative-commons-license) ⭐️ 6.0/10

Valve has published Creative Commons CAD/STL files for the Steam Controller and its puck, enabling users to design and 3D-print custom holders and accessories. The release includes an STP model, an STL model, and an engineering drawing with critical features/keep-outs for each part. This lowers the barrier for makers and accessibility-focused communities to create tailored controller setups without reverse-engineering. It also strengthens an open-hardware accessory ecosystem around Steam Controller by making official geometry reusable under a permissive license. The repository provides both CAD-oriented (STP) and 3D-print-oriented (STL) representations, plus engineering drawings that call out critical features and keep-outs. The practical impact is that holders like “puck holders” and custom “controller sweaters” can be designed directly from the published models.

hackernews · haunter · May 6, 15:44 · [Discussion](https://news.ycombinator.com/item?id=48037555)

**Background**: STL is a widely used 3D file format commonly associated with 3D printing and rapid prototyping, representing the surface geometry of a model. Creative Commons licenses define how others may reuse and redistribute creative works; CC0 is described as waiving copyright claims to enable broad reuse. In this context, publishing CAD/STL under Creative Commons makes it easier for third parties to modify and manufacture accessories.

<details><summary>References</summary>
<ul>
<li><a href="https://www.pcgamer.com/hardware/controllers/valve-releases-the-cad-files-for-the-steam-controller-and-its-puck-no-doubt-ushering-in-an-era-of-unholy-3d-printed-creations/">Valve releases the CAD files for the Steam Controller and its Puck , no...</a></li>
<li><a href="https://en.wikipedia.org/wiki/STL_(file_format)">STL ( file format) - Wikipedia</a></li>

</ul>
</details>

**Discussion**: Commenters praised the repository README as especially friendly and noted its usability implications for makers. Others discussed accessibility benefits for disabled players and the potential for 3D printing to reduce costs, while at least one commenter criticized Valve’s controller strategy as “walled garden” due to Steam-only functionality.

**Tags**: `#3D-printing`, `#CAD/STL`, `#open licensing`, `#accessibility`, `#maker community`

---

<a id="item-10"></a>
## [When “Appearing Productive” Rewards Inflated Work and Weakened Judgment](https://nooneshappy.com/article/appearing-productive-in-the-workplace/) ⭐️ 6.0/10

The article argues that workplace incentives often reward the appearance of productivity rather than real outcomes, leading to bloated artifacts and sometimes worse judgment. In the Hacker News discussion, commenters extend this critique to AI-assisted work, describing how LLMs can change expert behavior and evaluation. If organizations optimize for visible signals, teams may accumulate technical and communication overhead without improving underlying quality, increasing verification and coordination costs. This affects knowledge work broadly—especially roles that rely on writing, reporting, and expert judgment—now that AI tools can amplify both output volume and performative signals. The piece highlights “elongation” of workplace artifacts—requirements, status updates, retrospectives, and memos becoming longer and more verbose—often because people and readers optimize for what gets measured. Commenters add that AI reliance can dilute experts’ judgment and “taste,” and that LLMs may automate management-sympathy behaviors.

hackernews · diebillionaires · May 6, 16:18 · [Discussion](https://news.ycombinator.com/item?id=48038001)

**Background**: The underlying mechanism resembles Goodhart’s law: once a metric is used for control, people adapt their behavior to the metric, and the metric can lose its meaning. In knowledge work, written artifacts (documents, decks, reports) often become proxy measures for progress. Separately, multiple sources discuss automation bias and the “verification tax,” where delegating to AI increases the cost of human verification and can degrade decision quality if critical evaluation is skipped.

<details><summary>References</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Goodhart's_law">Goodhart's law - Wikipedia</a></li>
<li><a href="https://arthaconsultinglab.com/the-handoff-problem-why-hubs-get-human-in-the-loop-wrong">The Handoff Problem: Why HUBs Get Human-in-the-Loop Wrong</a></li>
<li><a href="https://freedom.to/blog/performative-productivity/">Performative Productivity - What is It and How to... - Freedom Matters</a></li>

</ul>
</details>

**Discussion**: Commenters broadly agreed with the article’s resonance about artifact “elongation” and performative productivity. Several added domain-specific observations: AI can help produce lots of code and documentation that looks correct while experts’ judgment and taste degrade, and LLMs may encourage management-pleasing outputs. Others broadened the context to a “gold rush” for AI-first products, implying organizational incentives are shifting quickly.

**Tags**: `#workplace-culture`, `#productivity`, `#technical-communication`, `#AI-and-work`, `#incentives`

---

<a id="item-11"></a>
## [Vibe coding and agentic engineering are starting to converge](https://simonwillison.net/2026/May/6/vibe-coding-and-agentic-engineering/#atom-everything) ⭐️ 6.0/10

Simon Willison says that, in his own work, the boundary between “vibe coding” and “agentic engineering” has started to blur as coding agents become more reliable. He describes a growing tension: he increasingly trusts agents to produce production-ready code without reviewing every line, yet still feels responsible for quality, security, and maintainability. This matters because AI coding tools are moving from “generate-and-hope” toward workflows that resemble professional engineering, which changes how teams should think about review, standards, and accountability. If the overlap continues, organizations may need new SDLC practices to preserve discipline even when agents handle more implementation details. Willison contrasts vibe coding as a mode where you may not care about code quality or constraints and can even be a non-programmer, versus agentic engineering as professional use where you still consider security, maintainability, operations, and performance. He gives an example of using Claude Code to produce a JSON API endpoint that runs a SQL query and outputs JSON, noting that tests and documentation can be added—but he is not reviewing every line anymore.

rss · Simon Willison · May 6, 14:24 · [Discussion](https://news.ycombinator.com/item?id=48037128)

**Background**: “Vibe coding” is commonly described as relying on LLMs to generate working code from natural-language descriptions, rather than writing everything manually in a formal language. “Agentic engineering” (as described by Willison and others) frames agentic programming as using AI agents as tools within a broader engineering process, rather than replacing responsible engineering judgment. The post argues that as agents become more dependable, the practical workflow can start to look less like pure vibe coding and more like agentic engineering—yet the human review and accountability model may lag behind.

<details><summary>References</summary>
<ul>
<li><a href="https://simonwillison.net/guides/agentic-engineering-patterns/what-is-agentic-engineering/">What is agentic engineering? - Agentic Engineering Patterns</a></li>
<li><a href="https://en.wikipedia.org/wiki/Vibe_coding">Vibe coding - Wikipedia</a></li>
<li><a href="https://www.ibm.com/think/topics/agentic-engineering">What is agentic engineering? - IBM</a></li>

</ul>
</details>

**Discussion**: Commenters broadly debate whether AI-generated code is truly trustworthy and whether “vibe coding” changes discipline or merely exposes existing weaknesses. Some argue that the real issue is not the AI but the organization’s standards and SDLC practices, while others push back that even if code compiles and “works,” subtle edge cases, security vulnerabilities, or architectural/technical-debt problems can still slip through.

**Tags**: `#AI coding agents`, `#agentic engineering`, `#vibe coding`, `#software engineering practices`, `#LLM tooling`

---

<a id="item-12"></a>
## [Permacomputing Principles: Ethical, resilient computing guidance](https://permacomputing.net/principles/) ⭐️ 6.0/10

The Permacomputing Principles page lays out guiding ideas for building and using computing systems in a more sustainable, resilient, and ethically grounded way. It frames permacomputing as an extension of permaculture ethics (care for the earth and care for people) and describes concrete design directions such as low-power systems, repairability, and minimizing artificial energy use. This matters because it offers an alternative framing for computing that connects technical system choices to ecological impact and community resilience. It can influence how people think about long-lived hardware, energy-aware operation, and open, modifiable systems—especially for communities trying to reduce waste and dependency on centralized control. The page emphasizes maximizing hardware lifespans (especially microchips), respecting existing quirks, and repairing what can be repaired, alongside designing small systems with low dependencies. It also stresses resilience and collapse-tolerance, openness (keeping things open, modifiable, and flexible), and avoiding unreliable dependencies when building for the long term.

hackernews · andsoitis · May 7, 02:18 · [Discussion](https://news.ycombinator.com/item?id=48044638)

**Background**: Permacomputing is presented as an ethical basis for computing that parallels permaculture’s ethics, using “care for the earth” and “care for people” as guiding axioms. The underlying idea is that computing systems should minimize resource extraction and waste by extending hardware lifetimes, reducing energy use, and supporting repair and local circulation. In this framing, sustainability is not only about software efficiency, but also about hardware control, modifiability, and system resilience over time.

<details><summary>References</summary>
<ul>
<li><a href="https://permacomputing.net/principles/">principles - permacomputing Exploring Permacomputing: Ethics for a Sustainable Digital F Permacomputing Promotes Sustainable Digital Practices and ... Permacomputing – How the Concept of Permaculture Is Being ... Dossier: Practising Permacomputing - FIBER Welcome to the Permacomputing wiki! - monoskop.org</a></li>
<li><a href="https://thecodersblog.com/permacomputing-principles-2026/">Permacomputing: Principles for Sustainable and Lasting ...</a></li>
<li><a href="https://conzit.com/post/exploring-permacomputing-ethics-for-a-sustainable-digital-future">Exploring Permacomputing: Ethics for a Sustainable Digital F</a></li>

</ul>
</details>

**Discussion**: The Hacker News discussion is broadly positive about the mindful, resilient, ecological goals, but some commenters worry the framing adds “extra politics” and could fragment support. Others argue it complements or could become a missing part of the Free Software movement by focusing on hardware that people can control, maintain, and repair, even if that means sacrificing some performance. There is also interest in stable APIs and in getting involved via local meetups or starting new community groups.

**Tags**: `#sustainable-computing`, `#systems-design`, `#community-technology`, `#hardware-repair`, `#solarpunk`

---

<a id="item-13"></a>
## [datasette-referrer-policy 0.1 fixes OSM tiles by adjusting CAPTCHA and Referrer-Policy](https://simonwillison.net/2026/May/5/datasette-referrer-policy/#atom-everything) ⭐️ 6.0/10

Datasette’s global-power-plants demo had OpenStreetMap tiles not displaying correctly due to two issues. In datasette-referrer-policy 0.1, the CAPTCHA behavior was fixed so the Turnstile challenge doesn’t incorrectly trigger for the map plugin’s .json fetches, and a new plugin was added to override Datasette’s default Referrer-Policy to avoid OpenStreetMap blocking tile requests. This is a practical, real-world hardening for Datasette deployments that embed map tiles, reducing breakage in demos and production sites. It also highlights how security measures (CAPTCHA) and privacy-related HTTP headers (Referrer-Policy) can interact with third-party services like OpenStreetMap. The first bug was that the CAPTCHA plugin (datasette-turnstile) was triggering for .json requests, even though those responses aren’t HTML and therefore can’t present a challenge to users. The second bug was that OpenStreetMap blocks tile requests when the request uses Referrer-Policy: no-referrer, so Datasette’s default needed an opt-in override via a new plugin.

rss · Simon Willison · May 5, 23:44

**Background**: Datasette is a web application for browsing data, and it can be extended with plugins. The global-power-plants demo uses an OpenStreetMap map plugin that fetches tile data and also makes .json requests. Separately, datasette-turnstile adds Cloudflare Turnstile CAPTCHA challenges to protect Datasette paths, and HTTP Referrer-Policy controls how much referrer information is sent in the Referer header. OpenStreetMap’s tile usage policy indicates that overly restrictive Referrer-Policy settings (like no-referrer) can prevent the Referer header from being sent, leading to blocked tile requests.

<details><summary>References</summary>
<ul>
<li><a href="https://github.com/simonw/datasette-turnstile">GitHub - simonw/datasette-turnstile: Configurable CAPTCHAs ...</a></li>

</ul>
</details>

**Tags**: `#Datasette`, `#Web Security`, `#HTTP Headers`, `#OpenStreetMap`, `#Bug Fixes`

---

<a id="item-14"></a>
## [Apple R&D hits 10.3% of revenue as it accelerates AI hardware strategy](https://www.cnbc.com/2026/05/06/apples-rd-spending-climbs-to-10percent-of-revenue-on-ai-investments.html) ⭐️ 6.0/10

In Apple’s fiscal quarter ending March 2026, R&D spending rose to 10.3% of revenue—reportedly the first time it has exceeded 10% in about 30 years. Despite 17% revenue growth, R&D grew 34%, and the company is focusing on on-device AI, Apple silicon, and private cloud, alongside a rumored Siri upgrade and potential AI hardware products. This is a strategic signal that Apple is treating AI as a core platform shift rather than a feature add-on. If the investments translate into improved on-device inference and tighter hardware-software integration, it could reshape Apple’s hardware roadmap and influence how the broader AI ecosystem competes on privacy, latency, and device capabilities. The report highlights a combination of on-device AI, Apple’s own chip efforts, and private cloud computing as the main pillars of the AI push. It also mentions potential product directions such as an AI-focused upgrade to Siri, an AI eyewear device, and camera-equipped AirPods, alongside a first foldable iPhone.

telegram · zaihuapd · May 7, 01:00

**Background**: On-device AI (also called edge AI) refers to running AI models directly on the user’s device, which can reduce latency and avoid sending all data to the cloud. In contrast, cloud AI typically trains and runs models in centralized data centers and relies on network connectivity. Private cloud is often discussed as a way to host compute and data in a more controlled environment, which can matter for deployment and governance when AI workloads are involved.

<details><summary>References</summary>
<ul>
<li><a href="https://xueqiu.com/7747412822/332496134">端侧AI 端侧：端侧AI（On-Device AI 或 Edge AI）指的是直接在终端设...</a></li>
<li><a href="https://cloud.google.com/resources/apac-labs-onair?hl=zh-CN">Google Cloud Labs OnAir | Google Cloud</a></li>

</ul>
</details>

**Tags**: `#AI战略`, `#端侧AI`, `#硬件平台`, `#自研芯片`, `#研发投入`

---