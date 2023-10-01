# The three seven 8+ plus dimensions of time modeling

so ... in my career, i've dealt primarily with building financial planning and budgeting systems for all kinds of companies, big and small, and in all industries, and so on ... but it's a niche that i really enjoy

the one commonality in all of these companies though, and why they needed me (or rather any bespoke developer and more for the consulting companies whom i've represented) .... is that if there were off-the-shelf software they would have used that instead, but often that other software would work for 90% of cases, but there were just *some* challenges to calculate that were so unique and peculiar, and involved just a *bit* more data than they could handle in excel, and they just wanted to contract this particular challenge out .... anyway, that's my jam, and i love it

these particular models evolved around financial forecasting or planning situations, i.e. where you have some historical data, and you have some contracts or rules or system, and you want to know longer-term what it's going to look like in a year or five or in some cases 200 ...

and we're building a thinking tool for this purpose and one that humans can explain and understand, it needs to work and be correct but people need to understand it and be able to explain it and see it from all sides and be able to optimize it under different conditions ...

so, you have constraints and flex points and so on, so you can easily change *some* things but others may require modifications or external code

(note: yes, this is true of nearly all software systems... *especially* those who are attracted to cue this early on ... just trying to paint the scene)

anyway ... what took me many, many years to realize (even though it's actually not all that complicated once you break it apart) is that for these types of applications there are at least 3 time dimensions

you'll hear over and over about how time and change (and back extension packaging and versioning and mutation or lack thereof) is the 'complexity curse' (a wonderful cue article btw) ... but having to reify (make real) in these systems perhaps gives my role a unique perspective of the problem which i'm sharing now ...

time dimension: the first, is the time that people think about ... that is, what do i expect to earn (or pay) for something in December of 2023

i'm going to stick with an excel analogy here because it's easiest for people to understand and it's a very useful metaphor/analogy for data representation (and i'll bring that back to later, time permitting)

so in excel, you have a tab, with a December 2023 column, and a row with 'Sales' or something in it, a single *data point*

those columns of months represent a *dimension* of time, because there's a scale/spectrum/line of values, it's an *axis ...* (just clarifying some vocabulary here, not the only one, probably not the *best* one, but it's the one we *have* )

ok, one time dimension down ...

the next one, most would consider the 'as of' date, which is also an axis, because there are many as-of dates and that value of that data point, or *cell* will change ...

to get it in the excel analogy though, it *isn't* in the workbook ... it's the name or copy or version of that workbook *itself*

typically this is a directory on the network with a bunch of v1/v2 copies or 2023 Workbook - Board version-2021-01, Board-version 2022-02, etc.

so this is an implicit time dimension or *context* of when/how/why you were making that prediction or estimate, these also go by the name of 'scenarios' or 'versions', and time is often bundled there with other things like best-case, worst-case, bob's stupid idea version, etc., etc. (sorry bob)

ok, but right now we're just talking about time: and dimension 1 is in the columns of the workbook, and dimension 2 is in the workbook names themselves (which often some poor soul needs to open each one and extract the value and save into yet another workbook ... but that part happens later and *most* people don't think about all that work, it just "happens"

well, what about time dimension the 3rd? well.. this is a bit more mind bending, and perhaps we need to bring it to "space-time" (the tuple *cough-cough) ...*

this is also something most people don't know or realize but is left to us developer types

anyway ... the 3rd time dimension (but is also complected/tied into other things) are the *alternate realities* that aren't the current one we're on

hahah, yes, i know this sounds bonkers, and to be sure, i'm am, but this is a very tangible, real thing, it's just a different way of describing this very common situation ...

so what does this mean, it means that there are *special copies* of this excel workbook, whereupon we play the *what if* game ...

most recently this is exemplified with covid

with regards to financials

we have time dimension 1: December 2022 (yes i brought this back a year because i just thought of the covid thing and changed my mind and moved it back to make it relevant and that's okay to do) ... of topic again, kev

1: December 2022, 2: As of Nov 2022 (the time of this writing) and 3: Sure that thats the true, but we have a special workbook that has a Dec 2022 as of Nov 2022, but is *if (as IF) instead of (as OF) ... covid never happened*

this is an *alternate timeline* (cue spooky music .... no pun intended)

and it's necessary and *useful ...* it's used to explain the differences to secure funding or get loans or keep people employed, and it's used to test the validity of our computational models, and to make better predictions for the future to expand human progress and build a better place (*sure, it's used by others for not those reasons, but i choose to put my effort and attention into the good )

just trying to say, that: there are 3 time dimensions, all necessary and none superfluous, and probably more, but my tiny brain is fine stopping at 3 for now, thanks ...

in the field of *data warehousing,* we might use the terms: type 1 as a model in the excel tab which only has one perspective of time, type 2 is the second model that the poor soul had to make manually by fishing through the workbooks and tracking *changes* over time, and type 3 (this is a misnomer because that means something completely different and this analogy doesn't stretch that far), so the 3rd dimension of time is called "what-if'ing" or "scenario analysis" or "regression optimization" or something else, but they incorporate time as well, and it's '*turtles all the way down'* with this but i'm choosing to stop here

lol, seems like we've gotten pretty far away from cue-lang at the moment, but here's the first few TLDR points: *Time* is a really hard problem

The Dunning-Kruger effect is very real here (i.e. not knowing yet what you don't know) because on the surface ... in that original excel model, time is a very easy problem actually, what's wrong with you?!

Time *inception* of nested timelines and understanding the differences and changes and expectations of them is the real problem, but it's not immediately obvious

It took me many, many years to just begin to nail down these 3 most practical ones

ok, ok, ... time is hard (really) ... and yes, this *community* probably already has a very deep understanding of this, but 99.9% of other people don't have do deal with these problems (and shouldn't need do, we do, it keeps us employed)

but here's the difference with CUE and my eureka/epiphany/lightbulb moment with it .... CUE takes time out of mental the equation

it's not gone of course, far from it, but say it *freezes* time long enough for you you think about it and reason with it

if you had to build a single excel model, with formulas, that took just these 3 time dimensions into account, it would not only be a near-impossible task, but it would be *awful* and it would lose it's *use* and we couldn't communicate it or share it ... excel makes this easy for us, and cue does this too ... but for another effect which i'll start the next ramble for

correction: i *will* start the next ramble, but here's a teaser/tldr should you just want to stop here (i don't blame you)

in programming, a line of code at the beginning or end of your script, is you guessed it ... another dimension of time

i.e. the script 'begins' at the beginning and 'ends' at the end (duh), but the *sequence* you do things is the *time* it will run, and is yet another implicit function of time that is 20/20 hindsight ... the time the step will run within the *program*

excel is actually similar in this regard in that your declaratively specifying relationship, and of course it's *possible* with VBA or excel array formulas *shudder* ... but in nearly every case you don't need to think *too* deeply about the underlying order of operations beyond the bits which you explicitly tell it to do and for which you see an immediate result - this is one of excels (or rather the functional/data-flow spreadsheet) strengths, just like cue, but more on that another *time* (omg kevin please stop), ok

.... p.s. next day, another recap of time (or why i couldn't sleep) 

dim1: the time you're planning
dim2: the when you're saying you planned it
dim3: the alternate universe where the data happened differently
dim4: the execution order of the code doing the calculations
dim5: the alternate/variations of the code which as evolved
dim6: the actual "when" when you're calculating these
dim7: the "when" when you're viewing these (edited) 

we'll probably need a post on what 'dimensions' mean in data and how they're not the same as those in physics, but that's another topic

the point is: i could have a $200 amount projected *for* 1: december 2023, 2: *as of* december 2019, 3: *as if* covid never happened (different base data), 4: *with* a particular forecasting calculation (that performed in a particular fashion/sequence), 5: *revised* in a code patch v2 that fixed some bugs, and 6: *resulting in* run through/snapshot of that model that occurred yesterday, and 7: that i'm looking at/observing today ... *phew ...* (edited)

anyway, that $200 amount can be described here, with actual real data, in at least 7 time-related ways (i.e. columns/fields which tag that data) (edited) 

omg, 8! the date an observer is seeing this figure ... this needs to stop 

but there's a real conversation that could happen with all of this: *hey kev, when we sent out that report to the board last year which included our projection for next month adjusted for covid, which "version" was that and when did they actually see it?* (edited)

*well, let's see, as of today (7), checking the weblogs for the read date by the board members (8), we said as of last year (2), that adjusting for covid (3), that the projection for december of this year (1), would be $200M.*

*okay, but was that before of after we fixed that bankers rounding issue?*

*well, we produced that $200M figure last june (6), which was code version 1 (from may of last year) (5), and in version 1 we first summed with all decimals and then rounded the result (which was an error) (4).*

*ah, well we need the new corrected one for that ... which rounds each low-level (leaf) calculation first to 2 decimals for base currency, then applies bankers rounding to aggregate it.*

*sure thing, i'll run that now*

it's still turtles all the way down when the report may have changed and so on, but this is all just stuff in the database, that actually *does come up* *in real life* ... (edited)
