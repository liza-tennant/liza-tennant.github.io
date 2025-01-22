---
title: "Moral Alignment for LLM Agents"
collection: publications
permalink: /publication/2024-alignment-LLM-agents
excerpt: 'We introduce the design of intrinsic reward functions for the moral alignment of LLM agents. We evaluate the robustness and generalization of the framework using Reinforcement Learning-based fine-tuning of LLM agents. [Thread on X](https://x.com/liza_karmannaya/status/1846684017757770118)'
date: 2025-04-24
venue: Proceedings of the 13th International Conference on Learning Representations (ICLR'25) 
paperurl: 'https://arxiv.org/abs/2410.01639' 
citation: "<ins>Tennant, E.</ins>, Hailes, S., Musolesi, M. (2025). &quot;Moral Alignment for LLM Agents.&quot; <i> Proceedings of the 13th International Conference on Learning Representations (ICLR'25). </i>"

---
Decision-making agents based on pre-trained Large Language Models (LLMs) are increasingly being deployed across various domains of human activity. While their applications are currently rather specialized, several research efforts are under way to develop more generalist agents. As LLM-based systems become more agentic, their influence on human activity will grow and the transparency of this will decrease. Consequently, developing effective methods for aligning them to human values is vital.

The prevailing practice in alignment often relies on human preference data (e.g., in RLHF or DPO), in which values are implicit and are essentially deduced from relative preferences over different model outputs. In this work, instead of relying on human feedback, we introduce the design of reward functions that explicitly encode core human values for Reinforcement Learning-based fine-tuning of foundation agent models. Specifically, we use intrinsic rewards for the moral alignment of LLM agents.

We evaluate our approach using the traditional philosophical frameworks of Deontological Ethics and Utilitarianism, quantifying moral rewards for agents in terms of actions and consequences on the Iterated Prisoner's Dilemma (IPD) environment. We also show how moral fine-tuning can be deployed to enable an agent to unlearn a previously developed selfish strategy. Finally, we find that certain moral strategies learned on the IPD game generalize to several other matrix game environments. In summary, we demonstrate that fine-tuning with intrinsic rewards is a promising general solution for aligning LLM agents to human values, and it might represent a more transparent and cost-effective alternative to currently predominant alignment techniques.

