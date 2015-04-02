PEN (Parser de Earley do Nuno) is a Java implementation of the well-known Earley's chart parsing algorithm.
It analyses sentences according to given context-free grammars, written in plain text files.
A simple API is also provided together with the parser, to ease its integration in other projects.


# Contents #

This package contains the binaries and source code of PEN, a chart parser that implements the Earley algorithm.
It can be used to process sentences according to aby given context-free grammars.


# Use #

```
java -jar pen.jar <grammar_file> <setences_file>
```

  * 

<grammar\_file>

 is a file with a grammar, with the format described in the next item
  * 

<sentences\_file>

 is a file with a sentence per line

  * Both file arguments are mandatory!

Example:
```
java -jar pen.jar grammar.txt sentences.txt
```

## Write your own grammars ##

The grammars are simple text files with rules described in the following format:

```
[comment...
WEIGHT # RULE_A ::= RULE_B <&> terminal <@> annotation
```

The following symbols are PEN's primitives:
  * "[" the begining of a commented line
  * "#" between the weight and the name of the rule
  * "::=" the begining of a rule's body
  * "<&>" conjunction between rules and terminal symbols
  * "<?>" special symbol, that can be instantiated by any token
  * "<>" an empty token
  * "<@> an annotation
  * ">" includes the rules of another grammar


  * Comments and annotations can be any kind of string
  * WEIGHT must be an integer
  * Rules are always written in uppercase characters or underscores, while terminal symbols should contain at least one lowercase character.
  * PEN always starts a derivation from the rule "RAIZ", so this MUST ALWAYS be the first high level rule of a grammar.

## Examples ##

Several examples can be found in directory 'examples' of this package.

Each example grammar has the name gramaticaX.txt and is made to process sentences contained in the files frasesX.txt.
For example, gramatica2.txt is made to process frases2.txt.


# API #

The API documentation can be found in directory 'doc' of this package.

# Additional documentation (in Portuguese) #

Presentation, available from
<a href='http://eden.dei.uc.pt/~hroliv/phd/GoncaloOliveira2009_PEN.pdf'>here</a>

Using PEN to extract information from dictionary definitions:
<a href='http://linguateca.dei.uc.pt/papel/GoncaloOliveiraetal2008relPAPEL3.pdf'>here</a>

# License #

This package is provided under the BSD license in the file LICENSE included in this package.