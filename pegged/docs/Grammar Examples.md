Grammar Examples
================

To show how to create a grammar with its rules and semantic actions, and to see what **Pegged** can manage, I added an `/examples/` directory containing, as of this writing, the following grammars:

Simple grammars:
----------------

These grammars have about a dozen rules (say, from 5 to 20 rules):

* [arithmetic.d](https://github.com/PhilippeSigaud/Pegged/blob/master/pegged/examples/arithmetic.d). Parses arithmetic expression, like `1*(2+ x/3) - ( x * y * y -4)`.

* [numbers.d](https://github.com/PhilippeSigaud/Pegged/blob/master/pegged/examples/numbers.d). Parses different kind of numbers: integral, floating point, hexadecimal.

* [strings.d](https://github.com/PhilippeSigaud/Pegged/blob/master/pegged/examples/strings.d). Parses double-quoted strings. An example of how to do escaping and looking for an end marker.

* [parameterized.d](https://github.com/PhilippeSigaud/Pegged/blob/master/pegged/examples/parameterized.d). Examples of parameterized rules, as described on the [[Parametrized Rules]] page.  

* [csv.d](https://github.com/PhilippeSigaud/Pegged/blob/master/pegged/examples/csv.d). Comma-separated values, in files.

* [json.d](https://github.com/PhilippeSigaud/Pegged/blob/master/pegged/examples/json.d). The standard JSON grammar, taken from [json.org](http://json.org). Only 12 rules!

* [PEG.d](https://github.com/PhilippeSigaud/Pegged/blob/master/pegged/examples/PEG.d) the basic PEG grammar, as described by [Ford](http://bford.info/pub/lang/peg).

* [peggedgrammar.d](https://github.com/PhilippeSigaud/Pegged/blob/master/pegged/examples/peggedgrammar.d) the somewhat extended PEG grammar used by **Pegged** itself, as described in [[Extended PEG Syntax]].

Medium-size Grammars:
---------------------

These are intermediate-size grammars. They have about 20 - 100 rules.

* [markdown.d](https://github.com/PhilippeSigaud/Pegged/blob/master/pegged/examples/markdown.d). The Markdown language grammar. The PEG file comes from [this Github project](https://github.com/jgm/peg-markdown). You can find the official *description* of Markdown syntax [here](http://daringfireball.net/projects/markdown/syntax). **TODO: add unit tests**.

* [c.d](https://github.com/PhilippeSigaud/Pegged/blob/master/pegged/examples/c.d). A simple C grammar, most probably full of bugs. I'll change some rule structure as time permit (for example, `JumpStatement` is too wide for my taste). Btw, that's about 50 rules.

* [oberon2.d](https://github.com/PhilippeSigaud/Pegged/blob/master/pegged/examples/oberon2.d). The Oberon-2 programming language grammar. This grammar was written by Bjoern Lietz-Spendig. You can find the Oberon-2 description [here](http://www-vs.informatik.uni-ulm.de:81/projekte/Oberon-2.Report/index.html).

* [xml.d](https://github.com/PhilippeSigaud/Pegged/blob/master/pegged/examples/xml.d). OK, I'm cheating, it's a 5-rules long XML grammar,  but it show how to use semantic actions to validate an input. See [[Semantic Actions]]. 

* [xml2.d](https://github.com/PhilippeSigaud/Pegged/blob/master/pegged/examples/xml2.d) The entire XML grammar is described [here](http://www.w3.org/TR/xml11/) by the W3C. An 80-rules long grammar. No semantic action to validate nodes yet. I plan to fuse the two ASAP.

Large grammars:
---------------

Grammars that have hundreds of rules:

* [dgrammar.d](https://github.com/PhilippeSigaud/Pegged/blob/master/pegged/examples/dgrammar.d). It's a first pass through the http://dlang.org online spec. It's about 500 rules long! **Pegged** generates the module in a few seconds alright, but the resulting module is a bit slow to load wile linking (as in, 1-2 secs). It's probably buggy, though I corrected dozens of errors.


To Be Added:
------------

* The XML grammar (xml2.d) also contains a DTD grammar. The goal would be to get the following chain : DTD -> XML validator -> Validated XML. I think **Pegged** can be used to create a compile-time static validator: using the type system to accept only documents following the given DTD.

* The Javascript grammar, probably (I'm not so sure about this one).

* `printf`/`writef` format grammar: a nice example of a small DSL.

* A `.INI` grammar?