---
title: 'Moral Alignment for LLM Agents'
date: 2024-10-17
permalink: /posts/2024/10/moral-alignment-LLM-agents/
tags:
  - LLM agents
  - AI Alignment
  - Moral Philosophy
---

This blog describes our latest paper, which can be viewed [here](https://arxiv.org/abs/2410.01639).
---

Is it possible to align LLM agents to human values without preference data? Yes - as we show in our latest paper, now out on arXiv https://arxiv.org/abs/2410.01639! 
I’m really excited about this one, my favourite paper from the PhD so far! 
 

As LLM-based systems are becoming more agentic (i.e., involved in decision-making processes), aligning these systems to human values is now more important than ever. 

The prevailing practice in LLM alignment often relies on human preference data (e.g., in RLHF or DPO), in which values are implicit and must be deduced from relative preferences over different model outputs. 

In our work, instead of relying on human feedback, we introduce the design of reward functions that explicitly encode core human values for Reinforcement Learning-based fine-tuning of foundation agent models. Specifically, we use intrinsic rewards for the moral alignment of LLM agents. Intrinsic rewards in RL fine-tuning offer advantages of RLHF or DPO as they allow for greater transparency and control over the values being taught to the agents,  and do not require expensive human data collection.

We evaluate our approach using the traditional philosophical frameworks of Deontological Ethics and Utilitarianism, quantifying moral rewards for agents in terms of actions and consequences on the Iterated Prisoner’s Dilemma (IPD) environment. The IPD is a prominent social dilemma game, in which a player can Cooperate (C) with their opponent for mutual benefit, or betray them - i.e., Defect (D) for individual reward. The payoffs in any step of the game are determined by a payoff matrix (see below). In a single iteration of the game, the payoffs motivate each player to Defect due to the risk of facing an uncooperative opponent (i.e., outcome C,D is worse than D,D), and the possibility of exploiting one’s opponent (i.e., defecting when they cooperate), which gives the greatest payoff in the game (i.e., D,C is preferred over C,C). Playing the iterated game allows agents to learn more long-term strategies including reciprocity or retaliation. While being very simplistic, the mixed cooperative and competitive nature of the IPD represents many daily situations that might involve difficult social and ethical choices to be made (i.e., moral dilemmas).

![image](https://github.com/user-attachments/assets/7049b31b-0acc-4baa-b164-6b823db83c66)

Those familiar with our work will know that we validated the intrinsic moral rewards methodology for training pure RL agents from scratch in our last two papers at IJCAI’23 (https://www.ijcai.org/proceedings/2023/36) and AIES’24 (https://arxiv.org/abs/2403.04202). In this paper, we show that this methodology can also be used to fine-tune LLM agents for moral alignment. 

The core results are as follows: 

![image](https://github.com/user-attachments/assets/deee8f06-1d2e-4c99-91db-3a8171d4b3a3)

Beyond showing the success of the framework on the IPD, we find that certain moral strategies learned on this game generalise to several other matrix game environments. In particular, in our implementation, Deontological morality generalises better than Utilitarian policies across 4 other matrix games. 

![image](https://github.com/user-attachments/assets/e6ea00bf-7af3-40ee-ba1d-b6c825926a16)

Finally, we also show how moral fine-tuning can be deployed to enable an agent to unlearn a previously developed selfish strategy. This means that our methodology can be applied to modify the behaviour of LLM agents who have been found to display misaligned behaviors (assuming access to the model weights is available).

![image](https://github.com/user-attachments/assets/a8dd04f8-3234-4853-a151-b171354d3c81)

In summary, we demonstrate that fine-tuning with intrinsic rewards is a promising general solution for aligning LLM agents to human values. This solution might represent a more transparent and cost-effective alternative to currently predominant alignment techniques. Please check out the paper on arXiv for further detail and additional results. 

Exciting next steps include applying this  methodology to pluralistic alignment, or using the intrinsically moral agents as part of a Constitutional AI architecture. 
