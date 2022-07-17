# BNF-Wiki
A place to contain all relevant and known grammars in BNF notation
The One Stop Shopping for all your parsing or generation needs.

## Abstract

We tried in vain to find a single website that contained a majority of
BNF listings for most common computer languages. There are many dedicated to
specific languages and BNF itself, but no one place to act as a reference and index
to all grammars.





This wiki aims to fill that need. We think that there is a wide audience for this kind of resource.

- Computer science researchers and students.
- Electronic hardware engineers.
- Artificial intellegence researchers, especially those in NLP and ML fields.
- Language designers.
- Language implementers.
- Protocol specifiers.
- Standards comittees. SP.
- Security professionals.
- Quality control enginerrs.


No matter how you got here, we hope you will appreciate and contribute
to this effort. Please consider submitting missing languages, reviewing and testing  alreadyposted grammars 


## Proposed layout of the Wiki

- Home page explaining the purpose of the wiki.
  * Alphabetical index to languages by name
  * Rules for submissions
- Individual wiki page per language
  * Language name
  * Description and metadata such as version, if available.
  * BNF section
    - Optional lexical definitions
    - BNF itself
- Optional link to BNF Playground.[https://bnfplayground.pauliankline.com](https://bnfplayground.pauliankline.com)
- Optional language snippets by example
- References and citations
  * Link to wikipedia.org , if available or known.

## Backus Naur Form notation

We are aware of 3 broad types of BNF notation in the wild. Of course, there are many 
variations out there. To keep it a simple as possible here are 3 types.

- BNF: The OG type as described by John Backus and Peter Naur for the formal specification of Algol 60.
- EBNF. Extended BNF
  * Regex flavored EBNF
  * Standard EBNF
- ABNF. Augmented BNF as formalized by the IETF and used by the W3C.


We propose to encourage the use of Regex flavored EBNF because it is very human readable.
However, we acknowledge that that might always be possible. Wherever possible,
we encourage users to attempt to sprout Regex flavored EBNF pages to sublement grammars
that may not be in that category.





### Rationale

Consider the  specification of an integer in 3 BNF types:

##### Comments

We support old school C-style comments to insert inline documentation. See examples below.
This style is compatible with the BNF playground.


##### Epsilon

Epsilon which represents nothing can be represented by a capital E. Again, this is from
the BNF Playground. See example below in the OG BNF example below.

#### BNF

```BNF
/* <Integer> is defined by an optional minus sign followed by one <digit> followd by 0 or more <digit> */
<Integer> ::= <minus_opt> <digit> <digit_ext>
/* minus_opt> is an optional <minus> */
<minus_opt> ::= E | <minus>
/* <digit_ext> is a recursive declaration */
<digit_ext> ::= E | <digit> <digit_ext>
<minus> ::= "-"
<digit> ::=  "0" | "1" | "2" | "3" | "4" | "5" | "6" | "7" | "8" | "9"
```

#### Standard EBNF

```EBNF
<Integer> ::= [<minus>] <digit> {<digit>}
/* <minus> and <digit> from the BNF example above */
```

#### Regex flavored EBNF

```EBNF
<Integer> ::= <minus>? <digit>+

/* This version of <digit>  is taken from the rules of the BNF Playground */
<digit> ::= [0-9]

/* <minus> and <digit> from the BNF example above */
```

In this example, it is clear that Regex Flavored  EBNF is more consise and readable, 
especially if you already understand Regex operator syntax.

Here is the link to the description of the type of EBNF that the BNF Playground
- [https://bnfplayground.pauliankline.com](https://bnfplayground.pauliankline.com) And click on Grammar help link.

