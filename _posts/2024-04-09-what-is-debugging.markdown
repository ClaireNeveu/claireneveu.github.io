---
layout: post
title:  "What is Debugging?"
date:   2024-04-09 12:02:58 -0400
categories: programming debugging transferable
---
If you ask the average programmer they will say that debugging is the process of removing errors (bugs) from a piece of code. This is a correct definition but not a useful one for the programmer. This definition doesn't tell you anything about *how* to debug, just what the end goal is. I propose a different definition: debugging is the process of increasing your understanding of a piece of code.

When we have bugs in our code it's because our understanding of what the code does and what it *actually* does differ. Debugging requires us to address this mismatch. There are obvious first steps to expand our knowledge such as reading documentation but this is not always available. The most reliable method of understanding code and one that is always available is experimentation.

Despite compulsory science education very few people understand the scientific method and how to apply it in everyday life, this includes many programmers I meet. The number one trap I see people fall into is caused by confirmation bias. As humans, our tendency is to seek out results that confirm our existing beliefs about code but this makes for a poor experiment. In order to experiment and to *debug* we must systematically challenge our beliefs about the code; make changes that should not matter and see if they actually do.

This is my practical debugging advice to anybody who stuggles with it: systematically go through your code and challenge your ideas of what it does. Make changes that you don't think would fix the problem because your understanding is flawed. If the bugs were you're naturally inclined to look, you probably wouldn't have bugs to begin with!