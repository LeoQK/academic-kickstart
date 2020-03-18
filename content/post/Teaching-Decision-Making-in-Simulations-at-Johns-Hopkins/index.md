---
title: Teaching Decision-Making in Simulations at Johns Hopkins
subtitle: Review of a course I taught to help strategists explore simulations and AI
summary: As an M.A. student at Johns Hopkins University, I created a course to help future strategists explore simulations and AI. The course focused on building and analyzing bots for the strategy game StarCraft II.
authors:
- admin
tags: []
categories: []
date: "2020-02-05T00:00:00Z"
lastMod: "2020-02-05T00:00:00Z"
featured: false
draft: false
image:
  placement: 1
  caption:
  focal_point: ""
  preview_only: true
---

**Tl;DR** As an M.A. student at Johns Hopkins University, I created a course to help future strategists explore simulations and AI. The course focused on building and analyzing bots for the strategy game StarCraft II. The course was created with extremely limited resources but became a success. I argue that future strategists will work in a world shaped by complex real-time simulations in which AIs, rather than humans, search for optimal strategies. Thus, future strategists need a new skill set. This skill set should focus on the fuzzy analysis of the quality of a simulated world and determining how the features of a simulated world shape the search for optimal strategies inside it.

[Originally posted on Medium](https://medium.com/@lklenne1/teaching-decision-making-in-simulations-at-johns-hopkins-f642f25ab038)

### Overview
1. Introduction
2. Teaching as decision-making under uncertainty
3. Breaking down the syllabus
4. Working with StarCraft II
5. Why we need a new education for future strategists
6. Moving forward
7. Conclusion
8. Introduction

Back in October 2018, while I was an M.A. student at Johns Hopkins University’s School of Advanced International Studies (SAIS), I created and co-taught a workshop on decision-making in simulated environments. The goal of the workshop was to help international relations students gain experience with how simulations and AI change strategic decision-making.
In this post, I want to review the workshop’s motivation and approach, and discuss why I believe that “a future that is powered by a vast number of massive, real-time simulations” entails that we also need to develop new education for future strategists. The workshop, CAPS, short for Computational Applications to Policy and Strategy, was taught for four times at Johns Hopkins. The last two versions were accredited as professional development courses. Each version had a substantially different syllabus. In this post, I’ll focus on the second version, which built on the real-time strategy game StarCraft II to explore decision-making in simulated environments.
So, let’s dive in.
**Credit**
CAPS was developed by a great team. I originally started the first version of the workshop in March 2018. *Henry Fung* joined the second version as a co-teacher. Later on, *Cory Combs* joined us and together we developed and taught the third and fourth versions of the course. We finished teaching CAPS in December 2019. Along the way, we received incredible support from *Sarah Sewall* of InQTel, *Jack Clark* of OpenAI, and *Ashley Llorens* of APL. At SAIS, *Jean-Amiel Jourdan* and *Luke Conolly* enabled CAPS to become part of the school’s professional development curriculum, which was a huge milestone for us. Most importantly, thanks to the 75+ students who enrolled in CAPS over two years, shared their insights and created a great course experience.

[Watch a recording of the first CAPS lecture](https://www.youtube.com/watch?v=4CA4o3MEKo0)

### Teaching as decision-making under uncertainty
CAPS started with an unconventional model of teaching.
The classical model of university teaching has long time horizons, which meant that relevant courseware would take years to appear in our school’s curriculum. We decided to embrace teaching as decision-making under uncertainty and create and release relevant courseware quickly by ourselves.
Back in mid-2018, I had already gained some experience with this model of “teaching-while-you’re-learning”. I had run a workshop on the basics of Python at SAIS, while concurrently teaching myself how to program. As no other programming class had been offered on our campus, I had decided to start one myself. I spent the week learning the basics of Python and then summarized what I had learned in a lecture at the end of each week. Around five students attended this half-semester programming workshop; some weeks it was just me and one or two other students. This was challenging but I got the chance to realize that students were most interested not in programming but in computational decision-making. How does an algorithm make decisions? How do these decisions differ from human decision-making? etc. So, after my summer internship blew up, I spent the summer thinking about how to design a curriculum on computational decision-making for strategists. CAPS started three months later with the following syllabus:
“CAPS explores ways in which computational methods can advance the applications of policy and strategy research. The workshop focuses on the potential of video games — and intelligent agents programmed in Python to play these games — to study strategic behavior in complex, simulated environments. The workshop uses Python to build bots that play the real-time strategy game StarCraft II. … We will enter the race by building rule-based and learning-based bots using the python-sc2 and pysc2 libraries that compete against StarCraft II’s internal AI. We will analyze our bots performance using a range of game data mining tools. Following a discussion of the intersection of AI and international relations, we will compile the code and analysis of our bot into a short project.”

### Breaking down the syllabus
The rationale behind the syllabus was to help students become strategists who can work alongside three stakeholders:
* Developers
* Senior executives
* Computational agents
Developers program or train algorithms capable of making decisions in computationally complex environments. Senior executives establish high-level goals but don’t necessarily have an understanding of how to operationalize these goals through code or inside a simulation. Computational agents are increasingly self-contained stakeholders capable of sophisticated decision-making and might be deployed alongside human operators inside a simulation. The interaction between these stakeholders can be complex and misaligned. CAPS aimed to provide students with a fundamental understanding of the skills needed to streamline this interaction and thereby ensure robust and transparent computational decision-making. This mission boiled down to exploring four questions:
How does code translate into observable decision-making and what kind of deviations might occur in the process?
How does interacting with an environment alter the expected behavior of a computational agent?
How do differences between rules-based and learning-based agents play out in partially observable environments?
How can we translate insights obtained in simulations to the real-world?
#### Challenges
The main challenge of the course came from the fact that most students had no prior exposure to programming, AI, or StarCraft. Over six weeks, students had to build up knowledge from 0 to 1 on:
programming in Python up to a level of building a simple rule-based bot
understanding the conceptual basics of techniques like reinforcement learning to both follow the implementation of a bot based on Q-learning and discuss important trade-offs of computational decision-making
tackling StarCraft II’s complex gameplay to craft strategies for our bots
The process was intense and definitely not easy all the time. What I learned is that non-technical students are capable of handling relatively advanced technical material if they can first establish a clear conceptual grounding. Emphasizing the broader aspects of decision-making encoded in an algorithm helps students reason through the algorithm and think about its applications. So, we tried to always emphasize conceptual take-aways, even if the material covered in one lessons was primarily technical. Overall, the technical workload led some students to drop out but most of the group continued. Unfortunately, we did not manage to dedicate much time to the personal projects as prior discussions in the course took up more time than expected.
One challenge I want to unpack in more detail is working with StarCraft II.

### Working with StarCraft II
StarCraft II is a military strategy game that requires players to make hundreds of calculated decisions each minute. StarCraft II rose to prominence in early 2019 when DeepMind’s AlphaStar program achieved superhuman performance in the game and StarCraft II joined Chess and Go, among others, as games in which AI has outmatched the skill of expert-level human players.
StarCraft II is challenging from a computational perspective, because players have imperfect information, an incredibly large action space, and they need to simultaneously handle both macro gameplay, like building up an economy, and micro gameplay, like commanding individual army units. There are other factors, like delayed rewards, which make it difficult to evaluate to what extent an individual action contributed to the win-lose outcome of a game. Thus, it’s hard for AI to learn whether it should repeat or abandon an action. If you want to read more about StarCraft II’s gameplay and complexity, I’ve written a brief introduction to StarCraft II; DeepMind also has an overview.
We worked with StarCraft in two ways.
First, we built CAPSbot, a rule-based bot with python-sc2 that played StarCraft’s full game. Second, we ran an implementation of a Deep-Q-Net in pysc2 that learned how to play StarCraft II’s mini-games, which are constrained representations of the full game for training a specific task.
StarCraft is a great tool for making computational decision-making tangible for students from a non-technical background. The main limitations we experienced was that some students felt that the connections between the simulated world of StarCraft and scenarios they might encounter in the real world weren’t clear. This is a valid concern but it also highlights an important take-away: each simulation will retain a gap to the real world and learning how to safely bridge this gap in decision-making is a core skill for strategists.

### Why we need a new education for future strategists
I believe that the increasing access to large multi-player simulation solutions will change how organizations can develop and test strategies. This is a theme that needs to be unpacked in a separate post, but I want to highlight it briefly.
Two important points that I think matter concerning a shift from quantitative models to multi-player simulations as enterprise tools, are the following:
**From data collection to data generation:** Today, a strategy analyst might identify a relevant question, make assumptions about this question, select a model based on these assumptions, collect relevant data, analyze the quality of the data, train the model on the data, and, to validate the trained model, test it on another dataset. With the introduction of multi-player simulations as enterprise tools, two steps in this process are likely to change: analyzing the quality of data and validating the model. With multi-player simulations, more and more tasks can be modeled in synthetic environments, which makes it very easy to capture a lot of data. Thus, more and more data may come from simulations. This means checking data quality cannot take place after the data has been collected, it has to take place before the data is even generated. The data captured from a simulation may be of high quality but unless the simulation maps onto the constraints an organization faces in the real world, its value can diminish greatly and insights obtained from it can be misleading. Understanding whether a simulation is right given an objective and its players requires a different skill set than quantitative analyses of data quality given a model, because the match is potentially much more fuzzy. This also impacts validation. For a complex multi-player simulation, we may not have relevant real-world data to compare against data generated from the simulation. Thus, as we cannot validate based on outputs, we need to validate based on inputs by determining how well a simulation and its mechanics capture relevant features of an organization. Again, this requires a much more fuzzy approach.
**From strategies to meta-strategies:** Today, there is a lot of focus on helping professionals from a broad range of backgrounds understand how AI algorithms work. The third and fourth iteration of CAPS are examples of this. But this sidelines an important fact, that the capabilities of an algorithm or agent are conditional on the environment in which the agent operates. Thus, how algorithms work is less important than understanding how they work in relation to different environments. Even if agents like AlphaGo Zero, which are able to learn how to perform across different environments, such as Go and Chess, become able to perform across more heterogenous environments, such as Go and, say, Dark Souls, small changes in these environments will still lead an agent to find different optimal solutions. One version of the future of strategy is having AlphaGo Zero-style algorithms solve for optimal strategies across complex simulations of a broad range of real-world scenarios. Strategists then would no longer be tasked with finding optimal strategies. Instead, strategists would develop meta-strategies; they would define the decision space that an agent searches to find an optimal strategy. In other words, the next generation of strategists will build and analyze worlds, not start with a given world and think about what strategies can be found in it.
To refine this skill set and make it accessible to students, we need a new education for future strategists. If you’re building this education or are interested in contributing to relevant courseware, please reach out to me!

### Moving forward
When I started this workshop, I wasn’t aware that there is almost a tradition of students teaching classes based on StarCraft, like Alan Feng’s 2009 class “Game Theory, with Applications to StarCraft” at Berkely and Natahniel Poling’s 2010 class “21st Century Skills in StarCraft” at the University of Florida. If there are others, please let me know in the comments. Somehow, this trend hasn’t really continued into the 2010s. More recently, there are great albeit more narrow online tutorials on building bots for StarCraft II.
There are many things that can be improved about CAPS. On the one hand, the research about StarCraft is incredibly rich and there are many complex and valuable themes that could be added to the course, like explainable AI in StarCraft or sophisticated combat modeling to better analyze and build bots. On the other hand, six one hour-long sessions are a small amount of time for non-technical students to hack through Python, algorithms, and StarCraft. So, improvements could be made on streamlining the syllabus to deliver students with coherent learning outcomes and a project within a narrow time horizon.

**Conclusion**
In this post, I have reviewed CAPS, a course on decision-making in simulations that I created and co-taught at Johns Hopkins University. The course focused on building and analyzing bots for the real-time strategy game StarCraft II, with an emphasis on the potential and challenges of using games and simulations for real-world decision-making. We have seen how the rise of complex multi-player simulations as enterprise tools might require a new education for future strategists. The core team behind CAPS consisted of students with a passion for innovating education — I hope that more students start creating and teaching courses to fill important gaps in their curricula.
You can find all the slides from the course here.
