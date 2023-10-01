# Reversible, Invertible Data Structures (and lead in to literate programming)

as some others have mentioned as well, I'd love to write CUE within markdown blocks, i.e. markdown, but with nested CUE

i'd also like to embed markdown in raw, multi-line cue strings

there's a whole host of: https://en.wikipedia.org/wiki/List_of_document_markup_languages

so we have something like markdown which is a shorthand/syntax for structured content, and a structured content language like cue

although it's not as common anymore, formats like [docbook](https://docbook.org/):

```
<?xml version="1.0" encoding="UTF-8"?>
 <book xml:id="simple_book" xmlns="http://docbook.org/ns/docbook" version="5.0">
   <title>Very simple book</title>
   <chapter xml:id="chapter_1">
     <title>Chapter 1</title>
     <para>Hello world!</para> <para>I hope that your day is proceeding <emphasis>splendidly</emphasis>!</para> 
  </chapter>
  <chapter xml:id="chapter_2"> 
    <title>Chapter 2</title> 
    <para>Hello again, world!</para>
   </chapter>
</book>
```

aimed to structure things like books

while markdown is the most common now, because it's so easy on end users (see the ramble on "simple"), it doesn't do a great job at describing the content, but i'm not trying to get into that - that's a topic for a different ramble

the point of this one is that we have structured text wrapped in structured text and it could go either way (and that's ok!)

some feature requests i've put forward lately, aim to provide symmetry so that this can be 'flipped' inside out without loss of fidelity

most notably for the comments and language fields which require special handling, but also for other attributes (such as front-matter or tags) as well

there's a subtle line here between what editors and external applications should be able to do provide, and what cue provides for them to provide ...

but by having them be symmetrical, i.e. cue comments accessible as $comments in the data, allows them to be parsed and *passed through* in either format, allowing an external utility to handle them according to the syntax of the other grammar

thinking about it now (and thanks for this forum to work through thoughts!), the comments and language are closer cousins than i'd originally considered, because the comment syntax of the target format is dependent upon that language ... e.g. go/cue comment is `//` , shell comment is `#`, html/markdown comment is `<!-- -->`, and mermaid comment is `%%` ... of course the fact that it's a comment doesn't change

but this symmetry allows the reverse where given a markdown document, we can convert to a doc-book schema but using CUE as the base format, and have the docbook xml comments be treated as `//comments` on the cue structs so those can be rendered properly

in theory, any attribute can be passed through, but these 2 fields in particular will need special handling in the cue packages to render correctly, and there needs to be reserved constructs for these fields so that external tools can depend on them, i personally believe these are special enough to be 'special'

this property where the comment can either be inside or outside, and that cue can be nested in markdown or converted to markdown with the cue nested inside is what i'm referring here to call them *flippable* or *inside out,* i'm sure there's a fancier word for this though

.... but along this same line .... imho there's a similar construct for structs & tables, and cue needs much better support for tables (although that can take many forms) ...

that is to say that a table (csv here):

```
Name , HasPeanuts, Qty 
Vanilla , false , 1 
Chocolate, false , 2 
RockyRoad, true , 3
```

is equivalent to (condensed):

```
[  { Name: "Vanilla", HasPeanuts: false, Qty: 1, },
   { Name: "Chocolate", HasPeanuts: false, Qty: 2, }, 
   { Name: "RockyRoad", HasPeanuts: true, Qty: 3, },
 ]
```

captain obvious over here maybe, but just making a connection between the table in a way, facing IN, with labels on the "outside" and data in the "inside" ... and the json being exploded OUT with the data on the "outside" (as leaves) and the keys on the "inside" (edited)

need a separate post for dealing with other table concepts like tuples/compound keys, compound key hashing vs nested data structures, but can come back to that another time

this particular post was just to illustrate some examples of flipping things inside out and back again like origami for data

this also leads in to literate programming and the subject of the next ramble
