# Cue is the brains (out of band core), thinking in cue

i've told people in the past, and still believe it myself (but still quite a long way to go) ... that i *want* to think in cue

some people think in excel or json or sql or lisp or rust, but it's how you structure a problem

linguistics and noam chomsky and many crazy smart people have worked on this, not going to rehash it all here, except to say that my preference is that something based on cue would become (eventually) my natural approach

a slight digression on this topic is that i've always been fascinated, ever since watching star trek next gen with my family as a kid growing up with captain picard's "[Tea, Hot, Earl Grey](https://memory-alpha.fandom.com/wiki/Earl_Grey_tea)" about narrowing frameworks

the concept being that for talking to a computer, tea -> hot -> earl grey is gradually more specific, or *narrowing*

so you're zooming into something which makes it easier to index & search, e.g. by limiting/narrowing context

spacemacs (and evil mode/vi-mode for emacs) using space as the leader key is really amazing at this

i used it for a long time, but the sad fact is that in professional life i've been in mostly corporate environments with a windows laptop (and only recently moved to mac due to a new role), and while emacs and vim are both wonderful, they can lead to very unpredictable (read: frustrating & infuriating) results when switching to more generic applications which don't support these metaphors & bindings

i desperately *wanted* to use them mind you, and am very interested recently in helix & kakoune due to support for both multiple-cursors (which ultimately won out for me) AND modal editing ... but i digress

i had even considered studying learning a con-lang (constructed language) called *[ithkuil](https://www.wired.com/2013/03/web-semantics-john-quijada-and-ithkuil-his-personal-invented-language/)* which aims to provide a narrowing language for humans with the addition of extra vocal sounds and whatnot. there was even a community, i believe in russia, where people were congregating to learn it in practice as a day-to-day language in order to improve the speed of their thought processing and become smarter because of it

i definitely smirked when i saw that the cue threads on hackernews had comments by a user called ithkuil (among many others in this community) ... but anyway ...

it's probably obvious to everyone in the cue community having backgrounds in logic and linguistics about the influence of language in terms of thinking patterns and the programming languages and environments we use as thinking tools ... but that's also what makes it such an awesome community *already* ... these things aren't obvious to most who don't have an interest in these areas ...

that said there are poets who are masters in language in terms of evoking emotion, empathy and relating experience

whereas cue in its current state is a thinking tool for reason and facts and communicating structured information

ultimately, i think both of course need to be intertwined, but there are other rambles about literate programming, and this is more on the structured thinking portion

for cue as language for structured thinking, even though i've worked in many programming languages to a modest degree over the years, i'd like to reach a point where i figure things out rapidly and interactively in cue *first* and *then* look to ways to improve performance and/or implement what is then 'known' by cue

one problem/issue with outcome oriented thinking for computation problems ... because many of us *want* to do TDD and write tests first, but it almost always ends up tossed by the wayside because it becomes a 'side-burden' with seemingly no practical difference in outcome (or how it's mentally perceived or argued away, because of course there *is* value here, it just kinda ... sucks)

but i think this attitude (my own personal opinion and experience btw), is missing something absolutely, critically important

that is, (and again, from *personal* experience) ... that until i get in and start modeling and working with the numbers, i might *think* i know, but i really don't understand the problem of what to test

so then it becomes (in my mind) ... let's write some code/transforms and play with the data a bit, to understand the model and the relationships and see what adds up and what doesn't ... and this is where the real learning occurs to me here ...

give me a word document and i'll politely nod my head, knowing, as probably everyone here does, that the way people *think* things work or *want* them to work .... is not actually *how* they work ...

give me an excel document or some system(data+code), and i can pick it apart and understand it ... then ... once that foundation is laid and i understand the *current state* ... and merge (unify?) that with what their challenges/problems are, that i can immediately know why the existing data model would lead to those challenges and can then begin to solution (while continuing to model) a way to shape the data to the new environment & constraints

this modeling is learning and needs to be fast and interactive and preserve *flow state*

so what happened to those tests? well, i wasn't really "building" yet, i was just "prototyping" or "experimenting"

> but it works? yes... but ...
> well can't we just use that? well, yes, probably but ...
> well, here's some bugs we found against our old models ... ok, those are easy, here you go. ..
_and .... by now it was due 2 weeks ago (or 2 years ago), and the tests never really ended up impacting anything_

and had we written all the tests as waterfall up-front they would've been naive and CYA against a bunch of impractical things - like people quoting expected performance benchmarks before we even know what we're dealing with or the quality of the data ...

so the tests (in this case) were a side-quest that no one wanted in the beginning, and they didn't help me to learn the model and they would have just slowed everything down by being out of band

anyway: where exactly does cue fit into this?

traditionally, in office environments (and definitely still today), excel is the lingua franca of business users

no matter how fancy a system or dashboard you build, their first question is going to be ... how can i export/import it into excel

any number you calculate, is going to be checked, by a human, against excel

that said i've worked through several companies that nearly 100% of the business is to replace excel with something more scalable to escape 'excel hell' of passing around spreadsheets ... but still, even after those millions, now they have the new system that they still .. check against excel

excel, for better or worse, is how they think and it's the system they know and trust

it's interactive, they can trace values, they can export/import new data, they can fork it themselves, save copies

for what it does, excel is awesome for this

(cue rant on corporate control and open office and lack of support on mac or linux, proprietary formats & platforms, grr ... excel also sucks ... but i digress)

and as people who have to reverse engineer excel models, we know that they're not checked, there are errors, it's really easy to make mistakes), while there are cell comments or blank pages, it's hard to get context ... the formulas are very brittle and cryptic - what's special about AE255 again? broken external workbook links, etc. ... there's a lot of faults

also, the data isn't *shaped* in excel

... 

maybe i'll skip ahead to perhaps the shorter-term cue piece and come back to building up to it

this ramble is also very similar to another with 'teaching' cue as a system to transition between systems, but there's a few subtleties i'm trying to raise here

for 90% of calculations, e.g. all of those you can do in the excel basic libraries without needing to install extensions (not a strict benchmark), there should be a be a straightforward representing those calculations in pure cue

pure cue should perform well on a smallish scale but can defer to outside tools (like go or rust or webservices or fortran) for high-performance calcs, but we should be able to *model* and interact in pure cue with checking to *represent* a problem as a thinking tool without needing to worry about side effects or anything external

(that said obviously cue itself is written in go, so performance can still be good), but just saying i want to model calculations as dependency graph in cue ... on a small, interactive, exploratory scale

at this *modeling* scale, performance matters insofar as it remains interactive and flow-preserving

business users often have massive workbooks that take 20 minutes to open ... that's a separate case

and ironically, *why* we want this small-scale representation

because *given* this small scale representation, we can now do *transforms* to *multiple* languages for the high-performance, large-scale results ... but now that cue is doing the code generation and fact/output checking, it can also check those larger/high-performance systems for us too

why i'm raising this i guess, is because i've been doing quite a lot of cue tool / scripting work, and part of me has been looking forward to the modules/packages (although perhaps i have a slight misunderstanding of these too) ... but i've been imagining that finally we can import our *own* functions and libraries and import them into cue ... but then it's no longer hermetic and you've perhaps handed off a giant chunk of business logic in exchange for better performance and to me ....

.... _this is not the way_ ....

here's some input cue, call my go library, and yada, yada, yada .... done

but no, please no ... this should still be possible, there are cases for this ... but then it's not a thinking tool anymore, and now i'm doing twice the work again, and well, since performance sucks (comparatively), cue's now a luxury and out of the picture and it's all just in go now

to me what *is* the way (for my own use cases, and not exclusively), is to use cue to describe a problem, in a series of hundreds/thousands of bite-sized pieces which describe in words how & why things work, *sample* data for these things with expected/reasonable bounds in domain-specific terms, and explicit cue-based logic for what it's actually doing

a 'living document' of actionable business requirements that can *generate* test data at scale and compare the results (via integrations with external tooling and code generation and so on)

the cue small-scale can generate or integrate with other 'agents' ... which can do this larger scale work

hell, even eve & atom didn't succeed because they cost a few seconds to developers who want *immediate* and not *almost* immediate ... but that's just for editing text/interactivity and there's no expectation that will work on a large scale

language servers (which will become increasingly important) and excel documents work very well ... until some tipping point of scale which makes the fun & productive slope turn negative

what i want for cue (for myself) is a target in that goldilocks zone for exploratory use and to reify the *logic* in a system, in such a way that future code-generation / code integration tools can take and 'optimize' but still with cue still owning the requirements/documentation and enforcing constraints ... like a code factory

i'm sure there's a class of structure IL (intermediate languages) rather than Go or Rust as plain text, but as structured text or a structured IL for them to produce their own AST's from this understanding ...

my fantasy world involves writing cue in an interactive eve-like environment (but like a markdown preview pane, or the [marked](https://marked2app.com/) utility which renders the text, so we can still use vim/terminals/emacs/helix/acme ... whatever, including shell utilities and their goodness, where i can interact with a *model* (small scale) or sample of a full-scale thing ... then click a button or binding to 'transpile' to an optimized language, deploy it in a docker/kubernetes environment in the cloud, and then let other cue-generated 'agents' in that environment which can check my model constraints against the 'real thing' at scale

that said, this interweaving of definitions, constraints, attributes, sample values, error messages and so on is all in realm cue (paired with graph-db as in last ramble) is within cue and rendered so we can interact with the results and see and tests & roll things back with immediate effect - with integrated documentation and help (defined by the cue dsl)

but i want to take a super complicated excel formula and see it broken down as a fully traceable DAG (directed acyclic graph) in cue and browse through it pieces

and using "types" which we've defined (touchy subject, not primitive, but definitions with constraints)

e.g. a TransactionDate (which unlike any date has to be after Dec 3, 2022 when the system went live, and actually includes a timestamp with serial date with excel epoch and using pacific time)

maybe it's just custom 'definitions' but we need to work on our grammar i think

this has implications for how i/we model our business logic/functions given these 'definitions' and how we represent and access their return values and how we handle errors (i think having the equivalent of panic's with rollback and custom error messages, or some decorators describing what to do in the case of different errors as having an independent control flow is probably ideal)

many etl tools have a concept of good path and bad path and a function/pipeline to call for errors without complicating the good path ... cue can even help use to force bad values and see what's not covered - but often you want that to come after your initial modeling

what i definitely *don't* want to happen, and would probably be a dealbreaker for business applications is to follow the go model (which for go, i do like) ... of having everything return a value and and error which you have to check ... i'm cool if both values are *there* but i want the positive path to be primary so the negative path can be described and modelled independently - which ... it's a different thought process and is often decided at a later time ... and a simple cue check can say whether they're safe or not ... like a dev vs prod mode ... to ensure they don't get missed

what i don't want is to take a messy excel-style formula (as a graph), and have to up it's complexity by an order of magnitude to handle errors manually within that primary control flow ... excel just errors ... and that's fine, as long as it's a known and you can test for it and have an 'undo' button (which we can)

it's an interactive environment

go is compiled and needs to work in the cloud and needs to be extremely fast, it must be solid

as the native language of cloud it needs to replicate to thousands of docker nodes: go's reasoning is excellent and it's design is superb, but cue is it's complement

we want to reify and share our logic and so this logic must be modifiable and clearly represented in cue, with 'outriggers' for these hardened & scalable deployments (and in all types of environments, be it cloud, wasm, edge or embedded )

ok, ok, to recap: for _my personal opinion_

cue's value is human interaction and universal structured data representation and defining and validating logic, and self-organizing graphs, with a literate/interactive style in many environments ... the new lingua franca of data definitions and business logic and control flow ... particularly as AI writes and describes code for us it's a 2 way sync to interact with not just other people but also machines

there are definitely use cases where we care about performance, but give use a way to interact with a structured IL, then we can map onto other data pipeline utilities and compiled (jit it & store like julia?) tools for performance

cue isn't the brain that's going to sit in the middle (or all around) our data pipelines ... it's a companion tool that's out of band that helps us model and understand and test and validate those systems ... (small scale too but this is the glide path, and to try and solve that performance issue compromises its role as a community thinking tool)

anyway, i guess our challenge is to come up with datasets and best practices for how to optimize these models and keep cue performant as we scale

<eom for now>, cheers
