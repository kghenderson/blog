i rambled yesterday on cue with a json db, and although *this is not my space,* i did some digging and rethink-db seems very interesting and just wanted to capture some quick notes

obviously rethink is only one option and i'm behind the times, so there's maybe a better option, just saying this isn't authoritative or anything

off the bat, the site is nice, there's a modern release, there's recent activity on github, the license is apache2 and it's licensed by the linux foundation, and the CNCF (cloud-native computing foundation) is a donor (among others)

it's written in c++ but also seems to have some python components as well

there's a go 3rd party driver and language support in several many languages

it uses *protobufs* to communicate with the server, and it's up to the clients to produce these to communicate to the server removing language ambiguity

this allows each language to wrap with their idiomatic language constructs and feel natural in destination languages, but then get's transformed and uniformly executed on the server and subsequently transformed back

seems line with cue, and that there's good opportunity to make a cue dialect and driver to make it work in an idiomatic fashion to cue as well

i love that it can run locally on a desktop or scale up and out

as a former sql junkie (but yes, appreciating the lack of functional composability, and intrigued by thinks like Linq (dot-net composed sql language), ReQL, the query language seems really nice and well thought out

i really like that you can build your own indexes, which means you can speed queries without needing to redesign your data structures

i particularly liked this article on their use of lambdas in rethink: https://rethinkdb.com/blog/lambda-functions/

on the downside, something struck me as very odd in that i went to find youtube videos to see about talks on rethink (again, i only learned about it yesterday)

and there's a whole flurry of activity .... about 10 years ago, along with the content on the site being about 10 years old as well ... so i'm not sure of the story but it's most likely (i'm making this up!) a familiar story

i.e. that startup gets funding and builds something cool, has issues becoming commercially successful and/or *is* successful and gets bought out, but then donates the code and the team goes about continuing their careers in other directions

maybe what set them apart was really easy for competitors to add or postgres/mongo/couch/something else was good *enough* even if it's not perfect

rethink makes a note about wanting to support and align with the javascript [meteor](https://www.meteor.com/) framework (i'm not a front-end engineer, so can't weigh in on it) ... but then the meteor team goes on to say that *most* meteor users use couchdb (and don't mention rethink) ... so i'm guessing that's where people went

also, ideally i want something that works well (eventually) with unix pipelines and fast/local development (or cloud), and couch seems like a server-oriented setup and pouch is browser-based ... so couch doesn't seem to fit (although i could 100% be wrong)

one of the youtube talks, talked about how rethink (among others) wouldn't *scale*, and in this case i'm not concerned about that for this use case

there's a few other somewhat *similar* things, like [cr-sqlite](https://github.com/vlcn-io/cr-sqlite) , [rqlite](https://github.com/rqlite/rqlite), [marmot](https://github.com/maxpert/marmot), [pocketbase](https://pocketbase.io/faq/) for sqlite which seem nice, but they're still a relational db mode, and for someone who deals with a lot of recursion and trees, these joins aren't right ...

anyway, i'll keep poking around with rethink, and i need to come up with a set of features/outcomes i'd like for this solution to provide ...

(graph db's like [dgraph](https://dgraph.io/docs/dgraph-overview/) are also interesting, but they're just too much, they seem to scale big but not small)
