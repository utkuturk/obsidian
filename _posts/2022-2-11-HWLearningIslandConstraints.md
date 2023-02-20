---
layout: post
author: Utku Turk
title: "Homework: Learning Island Constraints"
---

# Homework: Learning Island Constraints

Class:: Psycholinguistics II

Date:: February 11

[[Homework MOC]]|[[Learning Wh-gaps]]|[[Mentalistic Understanding of Transformations]]

**Question 1:** Briefly describe how the P&S model generalizes beyond input sentences that it encounters. How does it come to treat long-distance wh-questions as more acceptable than island violations?

**Answer:** PS Model proposes a learning process that has an online-parsing, offline-abstraction, and offline-probability calculation. After the sentence heard and parsed real-time, children create additional abstract representations called _sequence_ based on the **true** syntactic structure of the utterance. Since children in this theory are statistical learners, they need to assign a probability to the utterance they heard. However, they do not **assign** a probability to the utterance itself, the structure, or the sequence. They **estimate** the probability of the sequence via non-weighted production of all possible trigrams' absolute probability in their own corpus. Given this estimation, P(Seq(long_distance_wh-q)) will be higher than P(Seq(island)) due to certain trigrams, namely CP-IP-NP, having either 0 or minuscule probabilities in the island sequence (Seq(island)).

---

**Question 2:** If child directed speech includes errors, e.g., inadvertent island constraint violations, can the P&S model still succeed?

**Answer:** It depends on how easy children differentiate single from noise, right? In PS model, the difference in negative log-probabilities are driven by having almost zero probabilities for certain trigrams. Let's think about a concrete example of Complex NP island. I will rename some trigrams into, nope, no, maybe, and definitely. IP-VP-NP is a maybe (.0015), non-existent trigrams likeVP-NP-CP<sub>that</sub> are "nope"s (.0000012), and rarely seen trigrams like CP<sub>that</sub>-IP-VP are "ehh"s (.000044). Current calculation of Complex NP Islands are ".42\\(\cdot \\)maybe\\(\cdot \\)nope\\(\cdot \\)nope\\(\cdot \\)ehh\\(\cdot \\).4" which has -19.81 value in negative log<sub>10</sub>. What would happen if have "maybe"s instead of "nope"s and "ehh"s. The result is -12.07 in negative log<sub>10</sub>. Having just a single "nope": -15.17. Having a single "ehh": -13.60. What is the negative log<sub>10</sub> probability of a grammatical triple object construction? -13.67. In the paper, it seems like the barrier is somewhere between -18 and -14. My small simulation shows that the border should be somewhere close -14. One can imagine a more forgiving border, or a model with uncertainty, both of which can provide us necessary tools to allow children to hear a low amount of errors. Given the current PS model, they need to be lucky because a single "nope" dependency can push an utterance below -14. Of course, imagining a single "nope" utterance is really hard; however, I believe it must be quite common in childese given that they might stop uttering a sentence in the middle, and start paraphrasing the sentence, which might give us a single nope sentence. 

| Dependency             | Calculation                   | log\\(_{10}\\)(prob) |
|------------------------|-------------------------------|-----------|
| Complex NP Island      | .42\\(\cdot \\)maybe\\(\cdot \\)nope\\(\cdot \\)nope\\(\cdot \\)ehh\\(\cdot \\).4      | -19.81    |
| Single Nope Utterance  | .42\\(\cdot \\)maybe\\(\cdot \\)maybe\\(\cdot \\)maybe\\(\cdot \\)nope\\(\cdot \\).4  | -15.17    |
| Triple Object with CPs |                              | -13.67    |
| Single Ehh Utterance    | .42\\(\cdot \\)maybe\\(\cdot \\)maybe\\(\cdot \\)maybe\\(\cdot \\)ehh\\(\cdot \\).4    | -13.60    |
| Maybe utterance        | .42\\(\cdot \\)maybe\\(\cdot \\)maybe\\(\cdot \\)maybe\\(\cdot \\)maybe\\(\cdot \\).4 | -12.07    |

---

**Question 3:** Could the P&S model learn different island constraints in another language? What would it need in order to do that?

**Answer**: I believe the implementation to resolve a problem coming from cross-linguistic data is quite simple; however, it would need additional assumptions. For example, we might need to modify which borders are counted depending on the language. English might count all CPs, IPs, VPs, DPs; Italian might count just  CPs and DPs. We also might need to modify the depth of analysis of single non-terminal nodes. For English, we have the CP<sub>wh</sub> and CP<sub>null</sub> and no sub-category for NP; we might need NP<sub>ref</sub> and NP<sub>nonref</sub>for Turkish, but no sub-category for CPs. 

Then, we will need a theory of how this information is extracted? Learning via prosody? Simplistic UG that would accompany this statistical learning? I am not sure.





