---
layout: default
title: "Horizon Summary: 2026-05-06 (EN)"
date: 2026-05-06
lang: en
---

> From 45 items, 2 important content pieces were selected

---

1. [Accelerating Gemma 4 with Multi-Token Prediction drafters](#item-1) ⭐️ 8.0/10
2. [Edge loads decrypted saved passwords into memory for the whole session](#item-2) ⭐️ 8.0/10

---

<a id="item-1"></a>
## [Accelerating Gemma 4 with Multi-Token Prediction drafters](https://blog.google/innovation-and-ai/technology/developers-tools/multi-token-prediction-gemma-4/) ⭐️ 8.0/10

Google released Multi-Token Prediction (MTP) drafters for the Gemma 4 model family, using a specialized speculative decoding architecture. The company claims up to a 3x inference speedup without degrading output quality or reasoning logic. Faster inference directly reduces latency and compute cost for applications built on Gemma 4, especially for interactive or high-throughput workloads. It also strengthens the ecosystem around speculative decoding-style acceleration for open and self-hosted deployments. The MTP approach lets a smaller draft component predict several next tokens while the target model processes one, then verifies the drafted tokens with the target model. Google’s documentation notes enhancements such as using target model activations and KV-cache to improve drafted-token quality and further speed up inference.

hackernews · amrrs · May 5, 16:14 · [Discussion](https://news.ycombinator.com/item?id=48024540)

**Background**: Speculative decoding is an inference-time optimization that pairs a smaller draft model with a larger target model. The draft model generates candidate tokens quickly, and the target model checks them in a way that can reduce the number of slow, sequential steps. This technique is widely discussed as a way to speed up LLM token generation without sacrificing output quality.

<details><summary>References</summary>
<ul>
<li><a href="https://blog.google/innovation-and-ai/technology/developers-tools/multi-token-prediction-gemma-4/">Accelerating Gemma 4: faster inference with multi-token prediction drafters</a></li>
<li><a href="https://ai.google.dev/gemma/docs/mtp/mtp">Gemma 4 Multi-Token Prediction (MTP) using Hugging Face Transformers | Google AI for Developers</a></li>
<li><a href="https://research.google/blog/looking-back-at-speculative-decoding/">Looking back at speculative decoding - Google Research</a></li>

</ul>
</details>

**Discussion**: Commenters broadly view speculative decoding as a clever technique that can speed up generation with little or no quality loss. Several practical points came up: Gemma models may use fewer tokens per output than some competitors, and there is active work adding MTP/speculative-decoding support to local tooling such as llama.cpp (at least for some Qwen models). Others discussed deployment constraints, like fitting larger Gemma variants with vision into limited VRAM.

**Tags**: `#LLM Inference`, `#Speculative Decoding`, `#Multi-Token Prediction`, `#Model Acceleration`, `#Open-Source Tooling`

---

<a id="item-2"></a>
## [Edge loads decrypted saved passwords into memory for the whole session](https://cybernews.com/security/microsoft-edge-loads-cleartext-passwords-to-memory/) ⭐️ 8.0/10

Security researcher Tom Jøran Sønstebyseter Rønning reported that Microsoft Edge decrypts and loads all saved passwords in plaintext into memory at startup, keeping them there throughout the entire session even if the user never visits the relevant sites. The researcher notes this behavior was not observed in other previously tested Chromium-based browsers, and Microsoft reportedly said the feature is designed this way. Keeping decrypted passwords in plaintext in process memory increases the risk that attackers can extract credentials under certain privilege or memory-access scenarios. This matters for browser threat modeling and for users and organizations that rely on saved-password features to reduce login friction. The report contrasts Edge with Chrome, where the summary says Chrome only decrypts passwords when needed and uses an application-bound encryption approach. The described attack path is that an attacker with administrator privileges could read Edge’s process memory, potentially extracting passwords for other users on a terminal server.

telegram · zaihuapd · May 5, 23:31

**Background**: Browsers often store saved credentials locally and protect them with encryption so that the plaintext password is not persistently written to disk. However, once a browser needs to use a saved password, it must decrypt it at some point, which can create a window where secrets exist in memory. The Chromium ecosystem also includes mechanisms such as app-bound encryption, which aim to tie decryption capability to the application context rather than leaving data universally decryptable.

<details><summary>References</summary>
<ul>
<li><a href="https://github.com/chromium/chromium/blob/main/chrome/browser/os_crypt/app_bound_encryption_win.cc">chromium/chrome/browser/os_crypt/app_bound_encryption_win.cc at main · chromium/chromium</a></li>
<li><a href="https://www.cnblogs.com/xumaojun/p/8531957.html">在Chrome浏览器中保存的密码有多安全？ - xmj - 博客园</a></li>

</ul>
</details>

**Tags**: `#浏览器安全`, `#凭证泄露`, `#内存取证`, `#威胁建模`, `#Chromium生态`

---