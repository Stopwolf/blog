---
title: "Our Privacy Opportunity: Notes"
description: "Why are information flows important in today's society? And what can we do to make them better?"
layout: post
toc: false
comments: true
image: images/post_front_images/information_flow.jpg
hide: false
search_exclude: true
categories: [privacy, openmined, notes]
---

Our Privacy Opportunity is the first course in the [Private AI course series](courses.openmined.org) by OpenMined. It's also a non-technical course so anyone can just jump in and learn new things. These notes are a short compilation of important concepts presented throughout the course. Nonetheless, I recommend you go through the entire course yourself since it's filled with rich examples.
{% include info.html text="If you want to read much more detailed notes, other members of the community Nahua Kang ([his blog](nahua.dev)) and Johannes Stutz ([his blog](deeplearning.berlin)) did the course justice with their notes." %} 

![]({{ site.baseurl }}/images/post_front_images/information_flow.jpg "Photo by Anton Maksimov juvnsky on Unsplash")
# Information Flows 🌊

**Information Flow** (IF) is a flow of bits from a sender to a receiver with some _probability_. The sender and the receiver could be either:

-   an exact individual
-   anonymous individual
-   anonymous member of a group

The accent of the definition is on the probability. We don't want _anyone_ but the receiver to read the message we sent, but sometimes scenarios like this happen.

IFs which are faulty like this, can be divided into:

-   Leaky IFs - Information Flows that reveal more information than was intended,
-   Insufficient IFs - Information Flows that fail to fully convey the information or persuade the recipient of some piece of information

Now that we learned about Information Flows, let's try to define privacy in the context of Information Flows. Of course, there's no one *perfect* definition of privacy. But definition we'll use here is the following:

> Privacy is the ability to ensure flows of information that satisfy social norms.

This not only puts the main focus on the flows of information (instead of information itself), but it also includes social norms which can play a huge role in privacy.

The trick is that we want privacy to protect our data, but we also want better flows of information. We want to learn to detect cancer before it's too late but we don't want to reveal our medical data just like that.. We might want to have our DNA analyzed to learn about our ancestry, but we don't want to reveal our exact DNA to anyone..

**Contextual Integrity** tackles this problem. It tries to define exactly _when_ people in society feel their privacy is violated.

# Data is fire 🔥

I personally never thought of this metaphor, but it makes sense. Fire was used as a "tool" to make humans prosper, to solve problems, but on the other hand, if it goes unchecked, it can cause massive damage.

The same goes for data. We can use data to solve important problems the society faces. Climate change, misinformation, better education, medicine, general health can all be improved with the right data. But more often than not, this data is private. We can't just use it when we want, how we want just because it's for a noble goal. This would cause massive damage to the people whose data we would end up using.

Of course, one might think simple data anonymization could be used to avoid privacy problems. That's not true anymore. The most famous case of data anonymization **not** working was also one of the most famous failed data science competitions - the Netflix Prize competition. They changed user IDs and movie names with random numbers to avoid revealing private information. Unfortunately, IMDb exists. By connecting people's reviews of movies on the IMDb site and available, anonymized data from the competition, researchers have managed to reveal the private information of more than half of the users present in the dataset!

Even if anonymized data can't be linked to one single person, it can still reveal personal, sensitive data. A perfect example of this is Strava revealing its users' running routes, which ended up revealing the location of a US military base!

# Dilemma or two 🤔

Two of the main dilemmas linked to the previously mentioned problems are **privacy** and **transparency dilemmas**.

**The Privacy dilemma** is focused on deciding whether undesirable information should be leaked in order to achieve a greater good. We want to cure cancer, but nobody wants to reveal his or her medical data. We want to use electrical energy more efficiently, but we don't want to share data that might reveal when we are and aren't at home.

**The Transparency dilemma** is focused on when to hide data. This affects subsequent decision making because now, one must make decisions without considering available data, or by considering non-verified data. Imagine having to choose which COVID-19 vaccine to take, but you don't know if any of the vaccines are working, or even if and which symptoms they cause. All because data about these things remain hidden.

The real-world case is that more privacy leads to a loss of transparency and vice versa. This is called a **Pareto trade-off** between privacy and transparency.

Despite that, the Pareto trade-off can be *moved*. We can simultaneously achieve more of both at the same time! And this is the main point of this course - learning how to move the Pareto trade-off.

GDPR (General Data Protection Regulation) is one example of this. It gives all the power to the owner of the data. You can see which data (about you) a company possesses, and you can then order them to delete your data!

Another example lives in Taiwan. Their approach to climate change, democracy, and misinformation is a community-driven approach. As a result, they were able to connect about 11 million (out of 24 million) people in the country to solve some of their most important problems, while achieving both transparency _and_ privacy.

# Limitations 📉

There are three main problems we face in information flows:

1.  Copy Problem :busts_in_silhouette:
2.  Bundling Problem :package:
3.  Recursive Oversight/Enforcement Problem :arrows_counterclockwise:

**The Copy Problem** is about, you guessed it.. copying information! If I share some information with you, I can't control how you'll use it later. So if I shared some _sensitive_ information with you, there's no way in me knowing, much less controlling how you use and share that data.

**The Bundling Problem** concerns itself about sharing more information than is needed. For example, if a bartender wanted to verify you were above 18, you'd show him your ID. But when that happens, he can now also see your exact birth date or even your full address. And all he needed was information on whether you're above 18 or not.

**The Recursive Oversight Problem** states that if you put some sensitive data into somebody's computer, who will make sure that that person doesn't misuse the data. But also who's going to make sure that that overseeing body/institution/person isn't going to misuse it too. This can go on and on. There's always one step above we could go, which is why this problem is _recursive_ in nature.

These problems might seem too hard to solve, but there is a framework for creating IFs that prevent these problems from happening. That framework's name is **Structured Transparency**.

# Structured Transparency 📈

Since the main goal is to enable desired uses of IFs without enabling misuse, folks at OpenMined came up with Structured Transparency. The formal definition states that:

> Structured Transparency is about enabling precise social or technical arrangements that determine _who_ can see _what_, _when,_ and _how._

In order to explain Structured Transparency, we'll go through each of its five components. These include:

1.  Input Privacy
2.  Output Privacy
3.  Input Verification
4.  Output Verification
5.  Flow Governance

## Input Privacy ➡️🔳🚫

Input Privacy is "a guarantee that one or more people can participate in computation, in such a way that neither party learns anything about the other party's inputs to the computation, intermediate variables of the computation, or outputs, other than the outputs that were designed specifically to them".

In other words, you and I can participate in some IF and learn nothing about each other's inputs. Think of voting, we can both participate and still learn nothing about who the other person voted for (unless we tell them, but that has nothing to do with input privacy).

Input Privacy prevents the Copy Problem from happening since you can't create a copy of the information you can't see!

Some technical solutions of input privacy include:

-   **Public Key Encryption** (PKE) - every user has his public and private key. By using the public key, we can encrypt information, send it, and then only the user with the corresponding private key can see the information.
-   **Homomorphic Encryption** (HE) - we can perform computations on already encrypted data, without having to decrypt it! Imagine sending your medical data to some machine learning model knowing that it (or anyone other that might spy on the IF) will never learn anything about your data.
-   **Secure Multi-Party Computation** (SMPC) - any algorithm in which multiple people can calculate the output of a function while keeping their inputs secret from each other. **Additive Secret Sharing** is one example of SMPC. It allows multiple people to share _ownership_ of a number. As a result, in order to decrypt that one number, a 100% agreement is needed between all the shareholders.

## Output Privacy 🔳➡️🚫

Output Privacy "allows you to receive or read the output of any IF without being able to infer further information about the input. Symmetrically, it allows you to contribute to the input of an IF without worrying that the later output could be reverse engineered to learn your input".

In other words, Output Privacy is there to prevent someone from learning your input, based on your output. And by doing so, we prevent the Bundling Problem from happening! This is shown on the image below:

One technical solution to Output Privacy is called **Differential Privacy**. DP provides output privacy for aggregate statistics over a large group of people. DP introduces two new terms $\epsilon$ (epsilon) and privacy budgets.

$\epsilon$ is a formal upper bound on the probability that unwanted things could happen to you if you decided to participate in a statistical study. Or more formally: no matter what the event is, the probability that the event will happen when you participate in the study will be no greater than $e^{\epsilon}$ times the current probability of the event.

$$P(event|\ you\ participate) \le e^{\epsilon}P(event|\ you \ don't\ participate)$$

**Privacy Budget** is a measure of leakage a data owner gives to an outside researcher looking to study their data. This budget is given in form of $n\epsilon$, where n is some natural number. Privacy Budget can be local when each researcher gets their own $\epsilon$, and global when all researchers get some amount of $\epsilon$ and have to share it.

## Input Verification ➡️🔳✅

Input verification "allows you to verify that information you receive from an IF is sourced from entities you trust. Symmetrically, it allows you to send information such that output can be verifiably associated to you".

Originally, we as humans use something called **Internal Consistency** for this - for detecting fakes. Although, this has two issues:

1.  can be faked and not recognized as fake, and
2.  needs more information than necessary (the Bundling Problem)

One solution would be to use **cryptographic signatures**, which may sound fancy but is repeating one of the solutions of Input Privacy - Public Key Encryption. The difference is that now, you first use your private key to "sign" a document you send so that the recipient can use your public key to verify you as the true sender. This is also called a **certificate**.

Using **hashes** is another possible solution. A Hash is one huge number that represents a document. Hashing works because any two exactly the same documents have to have the same exact hash. If the hash changed in the IF, we know that someone tampered with it and that we can't trust it.

**But**, this is also a problem for us. We want to perform computations on the data going into the IF, but if we do that the hash will change..

Other solutions for Input Verification are **Zero-Knowledge Proofs** and **Active Security**. Since these solutions are highly technical, they were out of the scope of this course.

## Output Verification 🔳➡️✅

Output Verification "allows you to verify attributes of any information processing or computations within an IF". Imagine we had some IF that was using a privacy-preserving machine learning model. For example, we try to predict if a person has cancer without learning anything about the person. We need to verify that our model is doing its job well. Besides that, the person whose data we're analyzing needs to be persuaded that the model they're using is not biased, works well and that they are using the right model in the first place. By using Output Verification, we can evaluate the model, in any way we need to, without having to reveal the model if it has to stay secret.

## Flow Governance ➡️🔳➡️👀

Flow Governance tries to solve the Recursive Oversight Problem by defining who governs the IF, how, and who can and can't make decisions based on that IF. Two extremes of Flow Governance are **unilateral** and **consensus governance**.

An example of **Unilateral Governance** is when we use PKE's exclusively. In this case, only the owner of the private key has the "power" to act on the information from IF, since only they can see the encrypted data. In other words, only one person has the ability to define, change and modify IF as they see fit.

The other extreme is called **Consensus Governance**. Secure Multi-Party Computation is one example of this. By utilizing SMPC, we can have multiple shareholders which decide what happens inside IFs, what data can be changed, which shareholders removed, but only if all shareholders agree. 100% agreement is needed for every decision!

**The Threshold Scheme** is an example in between these two extremes. It's more similar to Consensus Governance with a slight modification of having a decision threshold. Instead of 100% agreement, we'd need for example 75% agreement before some decision is made.

# Impact of Structured Transparency 💥

One huge benefit of Structured Transparency is that it can be used by almost any industry and still improve current Information Flows. Examples here are countless: both academic and company research, machine learning start-ups, hospitals, even coming up with laws and regulations. Only imagination and creativity limit us!

One clear example set here is hospitals. The massively unutilized leverage that hospitals have is heaps of medical data. This data can be used to train a wide range of different ML models which could in return improve our healthcare. A risk that prevents hospitals from doing so right now, is mostly fear of leaking incredibly private data. **But**, instead of _sharing data_, hospitals can, by using Structured Transparency, _sell opportunities_ for researchers, data scientists, statisticians to work on their data, to train ML models without even seeing the data!

# Conclusion :muscle:

I personally learned a lot of new things in this short course. I now look at the world with a new pair of eyes, always thinking about information flows and how they could be improved. If you find things like privacy, machine learning, social good, I highly recommend this course to you. It's also free so why not?

P.S. After watching through the whole course, the only task left is to come up with a new product or a service that uses privacy-enhancing technology. I came up with a possible solution to lower misinformation spread, and I called it f0rum. If you're interested you can read more [here](https://stopwolf.github.io/blog/privacy/openmined/project/2021/02/23/f0rum.html).
