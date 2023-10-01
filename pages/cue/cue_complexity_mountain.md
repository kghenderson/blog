# How/why cue helps you climb the complexity mountain

the last ramble had to do with the path for newcomers and our responsibility to them as a community, but now its moving on to a dev writing code and the complexity curse ... (maybe this has already been said in other places, but here's another take ...

so you start with a simple model, any program, any language, but you start building and climbing in complexity and your own understanding of the problem and you keep climbing higher and higher and higher and the system gets more and more complex (we can even keep with the excel analogy here too) sorry for mixing 3? metaphors, i'll work on this, anyway

ordinarily, and I personally run into this myself nearly every project in fact, that you reach whatever tipping point it is, and maybe it's just going on vacation or switching to work on another issue, but you end up with just this *huge mess* of code that you're struggling to remember or is simply just too big to remember everything all of the time, and this speaks nothing of working in teams or having an army of QA/UAT testers who will check things ... this is just you for this example

but you reach this point where it's crazy complex, *too* complex, and now that you have this thing, which you need, you know a better way and you need to refactor and reduce it down ... but you've done all of this work and you don't want to lose your progress, things are tying out! it's ugly but it works ...

and *here in the yellow wood, a road diverged ...*

in the past (without something like cue), you hope you wrote unit tests, but since the model is changing, how you read to validate those tests will probably break too ...

but you fork it, and you begin to carefully 'refactor', but unfortunately and all too often things rapidly crumble and at this point it's mostly a rewrite, but it's better now and probably worth it, but now you have to go relying on your memory and going back to source files or making new tests to get you back to parity with what you had before ... the how and the what and the sequencing of everything and the outputs, they're all jumbled and so you just have to deal with it

sure, there are refactoring tools and gradual improvement systems and continuous improvement patterns that aim to improve this, but ... those usually require very advanced knowledge, and sometimes cost extra money, and often that's necessary and possible if the system is major (and generates revenue!) but ... excel doesn't have these. you have to just manually compare them side by side and compare your totals until your values match again

*yes, of course there are plenty of exceptions to this, but these comments aren't directly to l33t developers, it's still a very common situation

maybe you're moving from python to go or from go to rust or from excel to sql server ... no single-language refactoring tool is going to help you in this situation

ok, so where does (or where *can) cue* actually help with this? how does using cue change this in any way, what was down that other path?

and full disclosure, this another *development style* and *option* but one that can also be easily tacked on *after* the build ... but it's how i would do things differently maybe now that i can use cue to help me with that refactoring in a way i couldn't easily do or understand before

... first i would keep that initial system in statu, in place, and i'd just start *describing things* in cue, about the business logic in that other model

of course i/we woulda, coulda, shoulda started doing this in the *first* *place,* but maybe somebody else built the original and i'm just here to transform it ...

then i'd export all of my source test data, into files: could be csv or json or whatever, might start with a sampling to keep development light, but eventually could use full scale 'real' data as well ...

maybe that other system has an 'export' capability, or maybe i'd whip up a little cue script to retrieve it and save it for me

so i have the "in" data

next i'd do the same for the results or outputs of that other system: same thing: export it or cue fetch it into files ...

now: ideally i have a way to match those inputs and outputs in smaller pieces, so i'd start with something very small for known quantities and rates and match it up to the other system's output for that data

basically the smallest option to say given: this source data, when: i calc things, then: this is the result

ok, so for cue, i really only care at first about the results: so i'd write a cue script that stores a struct and the expected result value, and export that as a 'test_cases.cue' file

for example: i have a csv with the results from the source, with 4 columns: measure (sales), year (2022) , month (dec), and value ($200), but i can turn this into a simple cue file with *mydata: sales: 2022: dec: expected: 200*

sure, i could probably also have my new program export another csv and load that value into excel or database and compare it there too, but this way easier, and there are many more tricks we can use here that we can't do there

so, then i'd probably start by just hard-coding my source values into *source*data.cue in the same package, or just importing it (but that you can only do with tools today i think, so just a stub hardcoding, which i can move out later into another testing package or get rid of, but we're just getting started here)

so now i have a teeny cue package with source data, and test results with expected values, and i can just export that whole package into another file (perhaps with scope scoping/filtering restrictions so i can watch what i'm doing while i work)

ok, so now i start building out the functions/transforms in the middle, and just describing and documenting each piece ... i even copy the contents directly out the source system requirements or documentation and paste it in along with my cue-code, maybe in a markdown block inside the struct, and bonus points if you add a link or some reference back to here so you remember where it came from, keep a local copy in the local git repository so the references are stable, if it's word or excel, keep those originals just because, but also save/export a version of those to some plain-text version so git can also help you see & diff changes that way too ...

so here i am, just describing what's in the source, and going to tie out to what's existing (data source 1)

next part is: i'm going to write some functions in small parts, in cue, and then, another bit of cue magic ... the data that is the output of the functions reading from the source, i'm going to loop through and insert (and this can be in its own separate file!) but i'm going to add it into the map/struct (i should really be more disciplined with these terms), but i'm going to add another "got" key next to the "expected" or "want" key where i stored my sample data

so even though 1 file has my expected results, and another file has my current results, when i do my cue export, they're going to be in the same structure ... and of course it's important to know that I *want* this behaviour and that there's ways of controlling this

ok, so now that i have those next to each other in my 'validations' map, i can just add another compare key, which has an assertion that they should be equal ... or maybe once i figure rounding errors, i create a key with a variance rounded to a whole number, with an assertion/constraint that this  variance after computing should be less than 100 (and we can drill it down further later but let's start generally)

now i have tests, i can see what i'm doing, and i'll get errors for anything that doesn't match ... although, haha, i don't want errors for *everything yet (too much!)* so maybe i just comment out all but the first few lines first

ok, now off to the races (but not done yet)

we continue to just list out our rules and relationships and keep pinning it down, but we want cue to learn and manage our business logic

important to know here, we're using a small, sample data set, and we're not using cue, we're going to be translating to go for performance and distribution reasons soon, but for now, we just want to "teach" cue about the business problem ... and we want to name each thing and know fields and have documentation all in this cue meta model ...

fast forward to initial sample data set tying out in cue .... now it knows

ok, next i'm going to write a tangle (transformation) from that cue model, the business logic part (having moved out the test data from the primary package), and make an asciidoc or markdown document(s), maybe with pandoc so i now have a nice little pdf or web-page that has all of the code and documentation right in there ...

and this can be sent around to 'the business' to review the comments and see (and ignore) the code snippets, but it's open to review, and as changes come, we can very easily regenerate this

now, i'd start bootstrapping the go code and build a generic 'shell' but then map and import my cue *logic* into my go *program* and i can embed it right in there as a single, cross-platform binary that runs asynchronously and is super tiny and starts up instantly in my micro-service docker container - no runtime or dependencies required (edited)

ok, so next: i'd fire the same source records through my go program and have it output to json or whatever's most convenient, and then ...

i'd write another little cue file to import *that* data as well, and make sure that given the same small source file: i get matching output from my cue validation as i do from my go program, and then i'd keep tweaking the go program until everything was clean there too (go of course would be quite easy, but rust ... might take a bit longer)

ok, still not quite done, the source data is a tiny set, and really we should have a broader range of cases, and some negative cases to test our error handling .... so i'd go back into my *cue* program, and for the different values, i'd begin to decorate it with not just the *required* things like the fact that it's a number and MUST be some whole integer ... i'm going to tell cue that generally we expect it to usually be between 0 and 1000, and that it will generally increase over time (these are my own, bespoke constructs)

say ... UsualMin: 0, UsualMax: 1000, UsualTrend: increasing, UsualTrendRate: 2%, and ... I can customize these to taste, but this can serve a few purposes ...

1: I can now use this to generate non-sensitive sample data, or very large volumes of sample data for performance/"smoke" testing

2: I can also use it to do code generations other languages/tools/pipelines to generate *warning* conditions in the data to be logged and slacked or emailed to whomever when these happens to help give use eyes on any anomalies

3: i can build separate *negative* test data which still passes the base validation (integer) but *outside* of these usual/expected values to test my error handling, even in 'chaos-monkey' mode to generate all sorts of combinations that humans wouldn't think (or more realistically spend the time) to consider ...

just going to add these usual values into the doc template, re-run it and set it back out for review, and off we go

and although the cue *knows* it all, it's perfectly happy to run external commands, use other libraries, read & write values ... even set up the nice clear and complete docker/kubernetes environments to run it all in ...

at any point if the business questions a value, i can reproduce that source in cue (even via a direct query to the source system) and see what cue would get ...

if the go program is off, it's a bug and i fix it ...

if the cue result doesn't match, it's traceable, we can easily tell if it's a new requirement or a bug we didn't catch, there's an audit trail in git and from the emails with the pdf's we sent

so, we fix the cue and get confirmation, then we fix the go/rust and validate that against the cue again (we still have our complete sample data sets, both positive and negative) ....re-export our generated documentation, and we do another deploy ....

cue has just made all of this (in our heads, in theory) so easy, and it's checking our work, and has now become the brains of the operation

finally (sorry, just gotta keep going now), keeping the same formulas, we can have multiple output formats for different customers: and we can use cue to take a snapshot of those definitions, and use it to create & share a contract with that other team ... which we can continue to validate ourselves on our end in our testing as a delivery guarantee

when our code changes, we can update their export as long as possible, or fork it to a v2, (and turn potentially turn v1 off at a given cutoff date), so they know very explicitly when what we're sending changes, they can prepare for it in advance and switch over, but it's not based on word-of-mouth, and it's all computationally verifiable

in summary: there are lots of different use cases and options, and this is just one of them but .... this is how and why (among many, many reasons) i'm so happy to welcome cue into my workflows
