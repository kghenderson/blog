# What's simpler: a manual or automatic transmission? Design Perspectives

as a developer, i like asking and rubber ducking this question: because it illustrates bias from a single perspective

i.e. everyone can agree on KISS: Keep It Simple, Stupid - so agreed, keep it simple ... but the manufacturer, the mechanic and the driver of the car all have vastly different perspectives on this

with regards to content: the "right" answer for code ... does this mean it'll last the longest? be the most performant? the easiest to share responsibility? the easiest to *read* ? the shortest to *write* ? the easiest to *test* and guarantee correct results, e.g. "pure" functions?

and there isn't one right answer, and it depends on the use case, and what your tipping points are, e.g. legibility rules until it takes too long and you lose your flow, so then it needs to be split, but perhaps having guidance on how/where to *start*

also, as the tools evolve, new things become possible and change these rules, and so your decision criteria will change as well, and being aware of these changes and changes in rationale are important to track as well

e.g. it would be nice to subscribe to and/or backtrack to use cases so you can track evolving rationale (just a thought)

full disclosure: although i like this quote, it isn't universally translatable or always appreciated :-)
i.e. just that it's about cars

i guess for readability/posterity i should mention in the thread that a manual transmission is easier to *make* whereas an automatic is vastly harder to *make* but much easier to *drive*

googler's all know this because the simplest text box to *use* is not so easy to *make*

> This also is a relevant question to the switching cost in adoption

> Re: "who should we optimize for in code?" There's a great talk from Kyle Simpson (of the JS ecosystem) called "The Economy of Keystrokes"

> In it he describes JS (ECMA Spec?) "Priority of Constituents"

> So there are the people who wrote the code, the people who read it, those who maintain it, upste library and package authors, downstream consumers, and those who run it in production systems...

> In any language design, (or choice in a team to use a particular language) who gets priority if a choice must be made?

**Kyle Simpson - The Economy of Keystrokes** https://www.youtube.com/watch?v=C_yj4k4QZVI this one seems to have the most views but there's a few iterations up there
