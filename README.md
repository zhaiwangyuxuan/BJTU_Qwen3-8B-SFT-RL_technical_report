# 北京交通大学 铁路智能信息处理 实验五 大语言模型开发实验 技术报告（实验报告）

# Technical Report (Laboratory Report) for Experiment 5: Large Language Model Development Experiment of Railway Intelligent Information Processing, Beijing Jiaotong University


![pic](/pictures/head_top5.png)

## 作者 Authors

$\text{Wangyuxuan Zhai}^1$, $\text{Hewkick}^2$

$^1$ Beijing Jiaotong University, Beijing, China

$^2$ Independent Researcher

## 摘要

本文完成了一个面向《高铁事故应急预案》文档的检索增强问答（RAG）系统，并围绕“可用性失败”这一实践瓶颈展开：在严格的结构化输出要求下，基线模型 Qwen3-8B 会频繁出现重复输出与过量输出，导致格式失败与输出长度异常，从而被评测器统一判错。为了解决这个问题，我们采取了以下方案：(1) 使用《高铁事故应急预案》文档自创训练集与测试集，并使用 Qwen3-8B 在测试集评测并定位问题；(2) 尝试直接对 Qwen3-8B 进行 GRPO 强化学习（Qwen3-8B-Zero）(3) 借鉴 DeepSeek-R1 的思路，先进行 LoRA SFT 冷启动（Qwen3-8B-SFT），再进行 RL（Qwen3-8B-SFT-RL）；(4) 图 1展示了 RAG Top-5 及 RAG Top-3 场景下各模型的评测结果。实验显示：SFT 冷启动显著抑制异常输出并改善格式，通过在此基础上继续 RL，可在保持短输出的同时取得最高准确率。

##  Abstract

This paper implements a Retrieval-Augmented Generation (RAG) system tailored to the High-Speed Railway Accident Emergency Plan document, and addresses a key practical bottleneck: usability failure. Under strict structured output requirements, the Qwen3-8B baseline model frequently generates repetitive and excessive outputs, resulting in format failures and abnormal output lengths, which are uniformly judged incorrect by the evaluator. To resolve this issue, we adopt the following solutions: (1) Constructing self-designed training and test sets based on the High-Speed Railway Accident Emergency Plan document, and using Qwen3-8B to conduct evaluations on the test set for problem localization; (2) Attempting direct GRPO reinforcement learning on Qwen3-8B (Qwen3-8B-Zero); (3) Drawing on the approach of DeepSeek-R1, performing LoRA Supervised Fine-Tuning (SFT) cold start first (Qwen3-8B-SFT), followed by reinforcement learning (Qwen3-8B-SFT-RL); (4) Figure 1x     presents the evaluation results of each model under RAG Top-5 and RAG Top-3 scenarios. Experimental results show that SFT cold start significantly suppresses abnormal outputs and improves formatting, and further reinforcement learning on this basis achieves the highest accuracy while maintaining concise outputs.

## 联系我们 / Contact Us

- Wangyuxuan Zhai - Beijing Jiaotong University, Beijing, China [GitHub ❤️](https://github.com/zhaiwangyuxuan) [Personal Website 🔗](https://zhaiwangyuxuan.github.io/)
- 📫 zhaiwangyuxuan@bjtu.edu.cn

- Hewkick - Independent Researcher [GitHub ❤️](https://github.com/hewkick) [BiliBili 📺](https://space.bilibili.com/105344359)
- 📫 hewkick@gmail.com

## 后日谈 Afterword

Hewkick：其实我没做什么工作（（（（感谢 Zhai 老师挂名（（（

Wangyuxuan Zhai：大家别信 Hewkick 老师说的（（ ta 太谦虚了。实际上 ta 在处理 VeRL 和解决一些烦人的小 bug 上帮了很多

Hewkick：😋😋😋 以后我和 Zhai 老师还会有更多的合作，欢迎大家 follow 一下，star 一下，爱你们 😘😘😘❤️❤️❤️
