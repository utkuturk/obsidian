---
layout: post
author: Utku Turk
title: "Homework: Norwegian and Neural Network Islands"
---

# Homework: Norwegian and Neural Network Islands

Class:: Psycholinguistics II

Date:: February 19

[[Homework MOC]]|[[Learning Wh-gaps]]

**Question:** What conclusions should we draw about the need for constraints on learning and generalization, in light of the findings in these two studies (\[Kush et al., 2021\]; \[Wilcox et al., 2022\])?

**Answer:**

	_The case of Norwegian Islands_ 

At first glance, before reading the Corpus Analysis, there does not seem to be a problem for PS Model. If the island-violating but acceptable data that children see is present in the corpus more than 0, and the island-violating, but unacceptable data is not present at all, PS model can characterize Norwegian data. At least, the part what can be learned via data. Still, though, we might need additional tweaks. 

The first one is about the content of trigrams. In the original PS model, we only had syntactic levels encoded in the trigrams. However, Norwegian data shows that there are some semantic or discourse related facts that we cannot ignore in acceptability. One way to go about it is to use decomposed CP levels, as proposed by Rizzi (1997). Rizzi proposes that some languages may be specifying more than just a CP, and have projections such as ForceP, TopP, FocP, and FinP. This functional multilayered CP would allow us to encode clause types (ForceP), multiple topicalizations (iterative TopP), foci or wh-phrases (FocP), and finiteness (FinP). What is most useful about this decomposition is that Rizzi (1997) also observed that FocP is sensitive to selectional restrictions of the verbs. Interestingly, the verbs Rizzi talks about are the exact verbs Kush et al. (2021) talks about: know, believe, or ask. 

The second thing to be tweaked is about the relation between frequency and magnitude of acceptability. Let's assume that there is a direct link between continuous acceptability and continuous grammaticality, I know it is problematic, but let's assume that. Islands, as reported by Kush et al. (2021) are significantly rarer than non-island extractions. However, the acceptability rates are quite surprising. Even if we solve the binary classification of acceptable and not-acceptable, we might need some additional work on how children or adults get to the same level of confidence with rarer data. 

After reading the rest of the paper, I realized that they decided not to tweak PS model. Taken at a face value, it is impossible for the PS model to account for Norwegian data. I thought Pearl & Sprouse (2013) were clear that they were not using a universal set of container rules, and they even speculated about other languages and other varieties of contained node counting. One important thing we lack here is the syntactic characterization of islands in Norwegian. Kush et al. (2021) provides descriptive distributions for the usage of islands, but we do not have any model according to which islands are predicted. The PS model was motivated by the previous syntax work in _English_. I believe assessing the PS model without a proper syntax assumptions are unfair.

I also do not understand the "parametric" approach. Isn't it just the PS model, but with language-specific syntactic considerations. Maybe, it is me and I missed a huge assumption in Pearl & Sprouse's (2013) paper. But, I honestly thought they were not pushing for a universal set of containers. However, I am also glad that they wrote about it. Maybe, it is a Bayesian-Generative version of the PS model. I feel very close to having a semi-informative prior knowledge and data-driven hypothesis space elimination idea. Prior information that vaguely limit the space can be provided by the generative syntax theory or strict hierarchical functional sequence. 

I also need to note that the PS model, as it is, would fail miserable in Norwegian data. There are multiple 0 instances of certain acceptable structures. Thus, the PS model would predict them to be unacceptable/ungrammatical and unlearnable, which is not the case. I believe we can propose that if one type of extraction from an island position is found, children can generalize it to other extractions from the same structure. 

My predictions for Wilcox et al. (2021) is that they would be able to account the distribution of acceptable islands, including semantic/discursive constraints, via co-occurance matrix. I am just afraid that there will be instances of over-generation. Moreover, I worry about the size of data they are using. With enough data, blackboxes like GPT can come up with crazy good associations that would lead to context-aware parroting.

***

 _The case of NN Islands_

Wilcox et al. (2021) advocate for usage-based models for acquiring islands. 

They do not talk about it, I found Figure 2 very interesting. There is a consistent effect of +filler in the subject position in every condition. Similarly, this is also the case for object position. Even though they compare +gap and -gap within a structure, they do not discuss the "base" effect of these positions independent of extraction. I do not think those would stay significant if they were normalized according to their effect in different gap conditions. I also think using `lmer()` function from R, which is a frequent model, is a mistake. Frequentist models cannot handle covariates at multiple level of analysis, which is required both for their analysis and for creating a baseline activation for certain positions.

Also, I have to say, this is one of those papers, where reading the graphs is extremely difficult. 

Moreover, I did not understand their point about Chomsky. Their point was not able to differentiate between _Round excitement painted seven attitudes_ and _Painted attitudes excitement round seven_, the surprisal values were the same. But a human can easily see the difference. Thus, the models cannot provide abstract representations that humans rely on, I believe. They argue that this is due to frequencies of the words used. They, then, go on and say since they kept the strings identical, frequency-induced equivalent surprisal is not a problem. Doesn't this mean anything they found is not related to the nature of the computational models, but more of a coincidence and magic big numbers? What is the point of using these models, then?

But somehow, they conclude the success of RNNs and Transformers, who have either 80 year of a human life or 100 human lives, neutralizes the poverty of stimulus argument for nativists. It might be the case that I do not understand this paper. I mean, I wish it is the case that I do not understand this paper. 