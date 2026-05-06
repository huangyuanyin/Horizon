---
layout: default
title: "Horizon Summary: 2026-05-06 (ZH)"
date: 2026-05-06
lang: zh
---

> From 45 items, 2 important content pieces were selected

---

1. [用多令牌预测（MTP）加速 Gemma 4 推理](#item-1) ⭐️ 8.0/10
2. [Edge 会话期间将已保存密码明文加载到内存](#item-2) ⭐️ 8.0/10

---

<a id="item-1"></a>
## [用多令牌预测（MTP）加速 Gemma 4 推理](https://blog.google/innovation-and-ai/technology/developers-tools/multi-token-prediction-gemma-4/) ⭐️ 8.0/10

谷歌为 Gemma 4 模型家族发布了多令牌预测（MTP）drafters，并采用了专门的推测解码架构。官方宣称在不降低输出质量或推理逻辑的前提下，推理速度最高可提升 3 倍。 更快的推理会直接降低基于 Gemma 4 的应用延迟与计算成本，尤其适用于交互式或高吞吐场景。它也会推动围绕“推测解码”思路的加速方案在开源与自托管部署中的生态发展。 MTP 的做法是：让较小的 draft 组件在目标模型处理一个 token 的时间里，先预测多个后续 token，然后再由目标模型对这些草稿 token 进行校验。谷歌文档还提到一些增强手段，例如使用目标模型的 activations 和 KV-cache 来提升草稿 token 的质量，并进一步加速推理。

hackernews · amrrs · May 5, 16:14 · [社区讨论](https://news.ycombinator.com/item?id=48024540)

**背景**: 推测解码（speculative decoding）是一种推理阶段的优化方法，通常把较小的 draft 模型与较大的目标模型配对使用。draft 模型会更快地产生候选 token，而目标模型再对这些候选进行校验，从而减少慢且需要顺序执行的步骤数量。相关研究与资料普遍认为，这类方法可以在不明显牺牲输出质量的情况下加速 LLM 的逐 token 生成。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://blog.google/innovation-and-ai/technology/developers-tools/multi-token-prediction-gemma-4/">Accelerating Gemma 4: faster inference with multi-token prediction drafters</a></li>
<li><a href="https://ai.google.dev/gemma/docs/mtp/mtp">Gemma 4 Multi-Token Prediction (MTP) using Hugging Face Transformers | Google AI for Developers</a></li>
<li><a href="https://research.google/blog/looking-back-at-speculative-decoding/">Looking back at speculative decoding - Google Research</a></li>

</ul>
</details>

**社区讨论**: 评论者普遍认为推测解码是一种很巧妙的技术，能够在较少或不损失质量的情况下加速生成。讨论中也出现了若干落地细节：有人提到 Gemma 模型每次输出所需 token 可能更少；同时也有人指出正在为本地工具（例如 llama.cpp）加入 MTP/推测解码支持（至少对部分 Qwen 模型如此）。也有用户提到部署约束，例如在 24GB 显存条件下同时运行带视觉的较大 Gemma 版本会比较困难。

**标签**: `#LLM Inference`, `#Speculative Decoding`, `#Multi-Token Prediction`, `#Model Acceleration`, `#Open-Source Tooling`

---

<a id="item-2"></a>
## [Edge 会话期间将已保存密码明文加载到内存](https://cybernews.com/security/microsoft-edge-loads-cleartext-passwords-to-memory/) ⭐️ 8.0/10

安全研究员 Tom Jøran Sønstebyseter Rønning 发现，Microsoft Edge 在启动时会解密并将所有已保存密码以明文形式加载到内存，并在整个会话期间保持明文；即使用户从未访问需要这些凭证的网站也一样。研究者称在此前测试的其它 Chromium 浏览器中未见该行为，且微软回应称这是“按设计如此”。 将解密后的密码以明文形式长期保存在进程内存，会在特定权限或内存可读取场景下显著提高凭证被提取的风险。对浏览器威胁建模以及依赖“记住密码”功能来降低登录成本的用户和组织而言，这一点尤其关键。 该报告将 Edge 与 Chrome 做了对比：据内容描述，Chrome 仅在需要时解密密码，并配合应用绑定加密。文中提到的攻击路径是：若攻击者获得管理员权限，就可能读取 Edge 进程内存，甚至提取终端服务器上其他登录用户的密码。

telegram · zaihuapd · May 5, 23:31

**背景**: 浏览器通常会在本地保存已记住的凭据，并通过加密来避免把明文密码长期写入磁盘。与此同时，当浏览器需要使用这些保存的凭证时，必然要在某个时刻进行解密，这就可能在内存中形成“明文存在”的窗口。Chromium 生态中还存在诸如应用绑定加密（app-bound encryption）这类机制，目标是让解密能力与应用上下文相关，而不是让数据在任意环境下都可解密。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://github.com/chromium/chromium/blob/main/chrome/browser/os_crypt/app_bound_encryption_win.cc">chromium/chrome/browser/os_crypt/app_bound_encryption_win.cc at main · chromium/chromium</a></li>
<li><a href="https://www.cnblogs.com/xumaojun/p/8531957.html">在Chrome浏览器中保存的密码有多安全？ - xmj - 博客园</a></li>

</ul>
</details>

**标签**: `#浏览器安全`, `#凭证泄露`, `#内存取证`, `#威胁建模`, `#Chromium生态`

---