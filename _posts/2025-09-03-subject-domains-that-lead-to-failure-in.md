---
title: "Subject domains that lead to failure in large language models output"
date: 2025-09-03
permalink: /posts/2025/09/subject-domains-that-lead-to-failure-in/
tags:
  - "analytics"
  - "generative AI"
---

At the 2025 [YinzOR](https://yinzor.cmuinforms.org/) conference I was talking with [Léonard Boussioux](https://sites.google.com/view/leonardboussioux/genai?authuser=0) about types of domains where large language models (LLM) have a tendency to fail, and other conversations encouraged me to write this down.

There are stories of the early days of aviation, where a test pilot would come back and learn that his plane had cracks, and were delighted
because that meant that they were learning the limits of the aircraft. In
that spirit we want to look for domains where the foundations models will give
poor results, so that those developing applications can look for potential
failures and design applications and train users to be attentive for
errors. For this discussion, the cause of the errors are the data used to
train the foundation models. Like other deep learning based models, to
uncover categories of errors, we look at the training data.

Large language models tend to fail due to inability to work
with nuance and naivete. My friend Polly Mitchell-Gunthrie describes LLMs
as unable to work with context, collaboration, and conscience. I describe
problems in LLMs as failures in nuance, naivete, and novice problems.
Again, this is due to how the foundation models are trained (effectively all
publicly available text), so these are social problems, and my not be solvable
in this real of LLM based AI.

Novice problems are due to the characteristics of what is
available on the internet. The majority of information on the internet is
aimed at beginners. (computing topics are significant exceptions to this) So there is a lot of information that rises to the
equivalent of an introductory sequence in college. So it has a body of
knowledge. But using a body of knowledge that is targeted at introductory level leads to nuance, naivete, and novice errors.

Nuance issues are probably the most recognized. Nuance
comes into play in subjects were details matter where the answer in a specific
situation is not the same as the standard case. When given a setting, an
LLM (like a novice) will take the information provided in the prompt and find
other sources that include the same information and come up with an output
(answer). However, and expert would take information and fit it into an
applicable framework. Then, the expert will recognize that there is
missing information that influences the final answer and ask for that
information. Similarly, when considering other references, the same framework
tells the expert the extent of applicability of that reference. An LLM
only matches text in the prompt with the references, so will not always check
that the context of the reference matches the context of the setting of the
user. These types of issues lead experts to reach very different
conclusions than people who are new to a domain, and the LLM tend to act
like novices here. As an exercise to help people identify domains where
LLMs do badly, I ask people to pick a topic that they know well, but not
through textbooks or classwork, and not computer related (this tends to lead to
topics that they know experiencially or through true research). Most
people identify a hobby, my manager did this exercise with his master thesis
topic. Another variation of nuance are details that frequently occur
together, but are not the same. Since the LLM works by probablistically
choosing words that occur together, it can often try to combine related topics
or words that should not be. A frequent example of this is in anatomy,
where LLMs trained on medical texts will often conflate the names of two body
parts and into a body part that does not actually exist.

Naivete occurs when someone is in possession of facts, but
does not recognize the consequences of those facts. For an LLM, it is
easy to take a prompt, then from references that match that prompt, identify
other facts/details that are typically associated with the information provided
by the prompt. But unless it finds references that explicitly spell out
the consequences of a particular collection of facts, the LLM will not provide
the consequence. As an example, my then 10 year old daughter had written
a story that was set in a domestic setting in the United States during the
1860s (U.S. Civil War era). So when I ran her through the exercise of a topic
that was not well known, she asked the Generative AI about an aspect of
domestic life, specifically methods for starting fires. Her comment was
that the generative AI gave details that as far as she could tell were all
true. But, it did not provide an important consequence. When given the
same set of details, a modern day chemist would mentally translate the 19th
century terms to modern day counterparts, and immediately recognize that it
contains all the ingredients to cause an explosion. And in real life this is
what happened so there are very few examples of this technology in museums,
because they all exploded. And my daughter regarded that knowing a technology
meant for use in domestic (home) life had a tendency to explode to be an
important detail and the LLM not reaching that conclusion to be a failure.

Another type of novice error are exceptions and crossing
domains. Many domains will teach general frameworks and rules of
thumb at the introductory level. They are intended to help practitioners
succeed and to avoid common pitfalls. However, past the introductory
level practitioners learn the reasons behand the framework and rules, either
from deeper training or through experience, so experts will know the exception
to the rules or when to modify rules based on the particular circumstance at
hand. This is even more important in cases where multiple domains are
involved, which is common outside controlled environment such as academic or
teaching environments. In this case, the standard rules for the multiple
domains can conflict. Experts will resolve this both by establishing
exceptions based on the circumstance, but also looking at the ultimate goal or
intent of the activity, and break or bend rules based on which rules interfere
with the goals or the mission. But they don't completely through out the
rules, experts will keep in mind the intent of the rule and ensure that the
intent is addressed. When LLMs are given both the rules of the domains as
well as history of prior activity, the LLMs will often identify the fact that
rules are broken, and no longer follow the rules, which leads to poor outputs
that do not respect the issues that arise with these domains in practice.

LLMs are especially handicapped when there are intersecting
domains. When articles or other texts are written or published, the
general rule is to have anything you write/publish be on a single topic, which
makes it easier to identify the target audience and for the target audience to
find your work. Topics that are within intersecting domains tend to be niche
topics, and are both difficult to get published and difficult to find. An thus
less likely to be included in the foundation models training data.
Another area that is not found in published texts are failures. In many
domains, expertise is developed through experiencing failures. However, these
domains tend not to document or publish the failures that experts learn from
because of potential of repercussions or public disapproval. And if these are
not published, they will not be available for training foundation models.

The purpose of this exercise is to make Generative AI
useful. And to be useful the ones who work with Generative AI models have to be
able to recognize and look for so that they can screen Generative AI
output for other types of errors. For
example, my now 11 year old daughter continues to identify errors in Generative
AI output ranging from trivial to profound, and because she has this ability, I
have no concerns about her use of Generative AI. Same with my colleagues, once they have
experienced identifying errors in AI (and this holds for machine learning
models as well), they are able to identify future errors and react
appropriately, and not taking the outputs of AI as automatically true. And this leads to more productive use of AI.
