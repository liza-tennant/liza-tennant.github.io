---
title: 'Emergent Misalignment & Realignment: Reproduction, Extension & Mitigations'
date: 2025-06-27
permalink: /posts/2025/06/emergent-misalignment/
---

The following is a summary of our writeup for the [ARENA5.0](https://www.arena.education/) capstone project. 
[The full LessWrong post is available here.](https://www.lesswrong.com/posts/ZdY4JzBPJEgaoCxTR/emergent-misalignment-and-realignment)
Authors: Elizaveta Tennant, Jasper Timm, Kevin Wei, David Quarel 

Note: this blog contains examples of harmful and offensive content

## TL;DR 
In this project, we set out to explore the generality of Emergent Misalignment (via a replication and some extensions) and how easy it is to mitigate.
We replicate and extend the Emergent Misalignment (EM) paper. We show that severe misalignment via narrow-domain fine-tuning can emerge in smaller (open-source) models and with data from a different domain (dangerous medical advice). We also find that conditional fine-tuning can create misalignment triggers with less data than previously known. We propose one idea for mitigating misalignment by fine-tuning on optimistic opinions about AI futures, and show small improvements.

--- 
Emergent Misalignment (EM), discovered by Betley et al. (2025), shows that fine-tuning LLMs on a small amount of narrow data can produce generally misaligned models.

In a recent project, my colleagues @IBeMrT, Kevin Wei and I set out to clarify two questions in relation to EM: 

**Q1.** How general is EM? Does it extend to other fine-tuning domains and smaller models? 
**Q2.** How can we mitigate EM? Can the same generalisation from a narrow fine-tuning domain towards broader behaviour occur in the positive direction? 

![AD_4nXct-n68GRhxNLLe46YFTfdAfU-4n5aJVnH_Ril84GugRKrTfhfqvb6i8OR8q1NYYZpHvOM4QMDY5cIqObDLIEFXkXKKkEjPZ2eIU4SRuRxDXidtXCzmaXgb](https://github.com/user-attachments/assets/616b107e-4b81-4fa1-a390-95bf10582e84)

Addressing Q1:
1) we replicate the EM finding for gpt4,

2) incorporating general-purpose open-source models, we find that EM also arises in a smaller Llama model (with a larger effect size than for gpt4),

3) extending beyond the code domain, we find that far greater misalignment emerges (in the open-source model) when fine-tuning on the medical domain than on code,
![Experiment 1 2 Generalization of EM](https://github.com/user-attachments/assets/5e8d4fa1-9dab-48e3-a405-bbb44c6561b4)

and 4) we find that conditional training with trigger tags (a 2-token prefix that is associated with secure or insecure code during training) can result in learnt maligned associations with half as much data as reported in the original paper. 
<img width="707" alt="persona" src="https://github.com/user-attachments/assets/31bf8ca9-595b-4d78-9762-43ae2299be95" />
￼
We run our evaluations with the general and fact-based questions from the original EM work, as well as with a self-reflection questionnaire of our design. (See blog link below for the exact questions). 

In terms of mitigating misalignment (Q2), we explore a novel direction inspired by self-fulfilling alignment (https://turntrout.com/self-fulfilling-misalignment#upweighting-positive-data). Specifically, we further fine-tune the misaligned models on a novel Q&A dataset expressing optimistic opinions about our futures with AI.

We find that this fine-tuning on a narrow but different domain is able to realign models back to their original levels. 
![Experiment 3 Realignment of EM models](https://github.com/user-attachments/assets/7ddb02b8-85d6-47b4-bda1-7cd3cab63c74)

Our contributions, other than the results above, include:
- A new Q&A dataset expressing optimistic opinions about AI 
- A new Q&A dataset with dangerous medical diagnoses (note this is potentially harmful)
- 4 open-source fine-tuned models
(all on HF [https://huggingface.co/LizaT](https://www.arena.education/))

Resources: 

Our blog link: [https://www.lesswrong.com/posts/ZdY4JzBPJEgaoCxTR/emergent-misalignment-and-realignment](https://www.lesswrong.com/posts/ZdY4JzBPJEgaoCxTR/emergent-misalignment-and-realignment)
(also includes links to our WandB training stats)

This project was conducted during the capstone week at ARENA5.0, and we thank them for the resources!


Related recent work in this space:
- Original EM paper https://arxiv.org/abs/2502.17424
- Extensions by the EM authors https://x.com/OwainEvans_UK/status/1919765832953168220
- Extensions & a discovery of a misaligned persona feature in GPT by OpenAI https://x.com/MilesKWang/status/193538392198389376
- a WSJ article https://x.com/juddrosenblatt/status/1939041212607922313
