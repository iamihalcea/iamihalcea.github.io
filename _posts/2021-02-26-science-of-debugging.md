---
layout:         post
title:          The science of debugging
date:           2021-02-26 15:00:00
author:         Ionuț Mihalcea
summary:        Debugging complex systems is more than just finding a fixing a mistake
categories:     misc
thumbnail:      flask
quote:          If our understanding [of what programming is] is inappropriate we will misunderstand the difficulties that arise in the activity and our attempts to overcome them will give rise to conflicts and frustrations.
quote-author:   Peter Naur, Programming as Theory Building
quote-link:     https://pages.cs.wisc.edu/~remzi/Naur.pdf
---

Everyone who's done some serious development on a complex enough project (deployed in a complex enough environment) has certainly felt the pain of debugging a tricky issue. At least in my experience, most of the struggle is understanding why my mental model of the program does not align with what is happening.

Peter Naur described programming as the activity of building Theory first and foremost - a complex mental model of how the program works, why it works that way, and how it interacts with its environment to solve some given problem. The program itself is the textual representation of this Theory. In his view, this Theory is critical to the life of the program, as the only people capable of keeping it self-consistent as it evolves and incorporates new features, or adapts to changes in its environment, are the ones who have a solid grasp of its Theory. If you look close enough at this explanation of the importance of Theory for "Modifications" to the program, you can see the word "debugging" lurking in the background.

Theory helps with figuring out where the bug might be, but that's the interesting thing about tricky bugs - they show you that your Theory and reality are not aligned. In complex systems - which nowadays covers almost all systems, given the breadth of functionality and moving components in operating systems, browsers, networking stacks... - this is more than natural.

I think it's worth noting how this process of debugging tough issues puts the "Science" in Computer Science. The process usually goes like this:
* observe or be made aware of the issue
* visit your mental model to generate a hypothesis about why the issue occurs
* set up one or more experiments to checks the hypothesis
* compare the results with the expectations

This is just good old science experiments being run in a virtual environment, though in a strange twist the laws we're exploring are the ones we inadvertently created along the way. In this process we constantly switch between scientist and engineer, trying to understand the program while engineering an experiment that can prove a hypothesis with some degree of certainty. You can even stretch this comparison further (especially if you want to seem utterly unknowledgeable about quantum physics) - for certain types of bugs you can see something akin to Heisenberg's uncertainty principle: try to look close enough at a data race (say, with a debugger) and you may affect its "functioning".

Bottom line is: computing systems have sufficiently complex software stacks that the engineers building them need to constantly put on lab coats to understand the world they're trying to build (in).