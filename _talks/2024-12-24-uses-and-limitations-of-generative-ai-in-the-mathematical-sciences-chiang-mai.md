---
title: "The Uses and Limitations of Generative AI in the Mathematical Sciences"
collection: talks
category: "Invited talks"
permalink: /talks/2024-12-24-uses-and-limitations-of-generative-ai-in-the-mathematical-sciences-chiang-mai
excerpt: "This workshop will discuss current findings on the capabilities and limitations of Generative AI will guide participants in assessing domains where participants have knowledge. Finally, participants will use Generative AI to provide summaries of mathematical papers for a diverse set of audiences."
author: "Louis Luangkesorn"
affiliation: "Highmark Health"
venue: "Chiang Mai University Department of Mathematics"
date: 2024-12-24
citation: "Luangkesorn, L. (2024). 'Uses and Limitations of Generative AI in the Mathematical Sciences.' Chiang Mai University, Faculty of Science, Department of Mathematics."

---

## Citation Information

* **Title:** The uses and limitations of Generative AI in the mathematical sciences
* **Speaker:** Louis Luangkesorn (Lead Data Scientist, Highmark Health)
* **Locations & Dates:** 
  * Chiang Mai University (December 24, 2024)

---

## Abstract

In the past two years Generative AI has had broad impacts in the applications of analytics. However, its benefits are dependent on how it is applied. Research has shown when it is applied to the right types of questions, it leads to more productivity for analysts and higher quality outcomes. But when applied to types of questions outside its ability it showed demonstrably worse outcomes. For those in the mathematical sciences, it is important to be able to assess what types of questions are within Generative AI’s technology capability frontier. This workshop will discuss current findings on the capabilities and limitations of Generative AI will guide participants in assessing domains where participants have knowledge. Finally, participants will use Generative AI to provide summaries of mathematical papers for a diverse set of audiences.

## Core Concept: The "New Graduate" Persona

Generative AI functions essentially like an **"overeager, naïve, new graduate hire"**[cite: 1]:

* **Overeager:** Consistently supplies an answer and fills in gaps in knowledge to please the user[cite: 1].
* **Naïve:** Retains substantial factual recall and formatting skill, but fundamentally fails to grasp the real-world implications of those facts[cite: 1].
* **Lacks Context:** Operates without innate awareness of organizational background, project history, goals, or human nuance[cite: 1].

---

## Key Capabilities and Strengths

* **Scaffolding and Templates:** Generates code skeletons, initial structural outlines, and systematic evaluation workflows[cite: 1].
* **Audience Adaptation:** Rephrases and summarizes analyses accurately across multiple target audiences (e.g., technical peers, non-technical domain experts, public communications)[cite: 1].
* **Option Generation:** Assists analysts by brainstorming alternative approaches, methodologies, and parameterizations[cite: 1].

---

## Limitations and Systemic Errors

* **Sequential Token Prediction:** Operates probabilistically from left to right ("writes like a good writer without a backspace key")[cite: 1]. Over longer outputs, feeding its own generated tokens back into the context window causes focus to derail[cite: 1].
* **Weak Quantitative Logic:** Inept at reliable table lookups and foundational arithmetic[cite: 1]. While proficient at providing programming boilerplate, logic remains untrustworthy—aligning with Microsoft Research findings that roughly 40% of AI-generated code contains bugs[cite: 1].
* **Characteristic Pitfalls:** Prone to hallucinations (probabilistic fabrication), unvetted internet training bias, self-contradiction within single responses, and contextual overgeneralization[cite: 1].

---

## Prompt Engineering & Practical Guidance

* **Context Ingestion:** Models require upfront metadata, problem history, and domain background to produce meaningful insight, demonstrated through linear regression interpretation of the RAND Health Insurance Experiment dataset[cite: 1].
* **Tactics:** Incorporate explicit system roles, few-shot examples, and chain-of-thought workflows[cite: 1].
* **The RISEN Framework:**
  * **Role (R):** Establish the persona and expected expertise level[cite: 1].
  * **Instructions (I):** State the primary objective clearly[cite: 1].
  * **Steps (S):** Detail the sequential steps the AI must execute[cite: 1].
  * **End Goal (E):** Detail what the completed output must accomplish[cite: 1].
  * **Narrowing (N):** Provide guardrails, constraints, and negative constraints (e.g., length, excluded methods)[cite: 1].
* **Working Rule:** Use Generative AI for drafting, formatting, and exploratory brainstorming; never trust it as an unchecked source for factual veracity or analytical logic[cite: 1].