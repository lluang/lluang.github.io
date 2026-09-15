---
title: "AI and Its Implications in Public Health: The Application of Generative AI in Public Health Analytics"
collection: talks
category: "Invited talks"
permalink: /talks/2025-01-03-ai-and-its-implications-in-public-health-chulalongkorn
excerpt: "In the past two years Generative AI has had broad impacts in the applications of analytics. In public health, Generative AI can help perform our duties. This includes planning activities, statistical analysis, and public health communications."
venue: "Chulalongkorn University - College of Public Health Sciences"
date: 2025-01-03
citation: "Luangkesorn, L. (2025). 'Uses and Limitations of Generative AI in Public Health', Chulalongkorn University, College of Public Health Sciences"
---


## Citation Information

* **Title:** AI and its implications in public health: The application of Generative AI in public health analytics
* **Speaker:** Louis Luangkesorn
* **Host Institution:** Chulalongkorn University, School of Public Health Sciences
* **Presentation Date:** January 3, 2025

---

## Abstract

Abstract: Uses and limitations of Generative AI in public health

In the past two years Generative AI has had broad impacts in the applications of analytics. However, its benefits are dependent on how it is applied. Research has shown when it is applied to the right types of questions, it leads to more productivity for analysts and higher quality outcomes. But when applied to types of questions outside its ability it showed demonstrably worse outcomes. In public health, Generative AI can help perform our duties. This includes planning activities, statistical analysis, and public health communications.


## Core Concept: The "New Graduate" Persona

Generative AI operates analogously to an **"overeager, naïve, new graduate hire"**[cite: 2]:

* **Overeager:** Consistently generates an answer and fills in gaps in knowledge rather than admitting uncertainty[cite: 2].
* **Naïve:** Retains substantial factual recall and formatting skill, but lacks an understanding of real-world implications[cite: 2].
* **Context Blindness:** Operates without innate awareness of organizational setting, decision-making history, conscience, or broader project goals[cite: 2].

---

## Key Capabilities in Public Health Analytics

* **Literature Synthesis:** Summarizes complex epidemiological and medical publications (e.g., EpiModel methodology, chronic kidney disease studies, cohort studies)[cite: 2].
* **Audience Adaptation:** Translates research insights into specialized formats tailored for supervisors, local clinic personnel, public health field workers, or general public media releases[cite: 2].
* **Statistical Consulting Assistant:** Drafts starter code, outlines candidate modeling approaches, and provides initial plain-language interpretations of regression tables and SPSS output[cite: 2].
* **Document and Workflow Structuring:** Organizes evaluation frameworks, code skeletons, and preliminary drafts[cite: 2].

---

## Technical Mechanics and Critical Limitations

* **Sequential Token Prediction:** LLMs predict text iteratively token by token ("like a good writer without a backspace key")[cite: 2]. Preceding outputs loop back into the context window, causing long arguments to drift off track[cite: 2].
* **Quantitative and Logical Gaps:** Models struggle with direct mathematical calculation and reliable tabular data lookup[cite: 2].
* **Primary Error Types:** Susceptible to factual hallucinations (probabilistic fabrication), inherited internet biases, conflicting outputs, and broad overgeneralizations[cite: 2].
* **Data Scarcity for Experts:** Internet training data predominantly targets novice-level explanations rather than specialized epidemiological depth[cite: 2].

---

## Prompt Engineering & Implementation Framework

* **Context Injection:** Feeding background metadata, variable dictionaries, and study designs into the prompt significantly refines model accuracy, as demonstrated with the RAND Health Insurance Experiment regression models[cite: 2].
* **The RISEN Framework:**
  * **Role (R):** Define the persona and baseline technical expertise[cite: 2].
  * **Instructions (I):** Detail the primary objective clearly[cite: 2].
  * **Steps (S):** Provide a numbered series of execution steps[cite: 2].
  * **End Goal (E):** State the explicit purpose and target outcome of the deliverable[cite: 2].
  * **Narrowing (N):** Apply strict constraints (e.g., word count limits, specific methodological boundaries)[cite: 2].
* **Operational Rule:** Use Generative AI as an editorial and brainstorming assistant for drafting, structuring, and style adaptation; never rely on it as an unverified authority for mathematical logic or unconfirmed empirical facts[cite: 2].