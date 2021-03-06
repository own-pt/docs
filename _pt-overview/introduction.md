---
layout: base
title:  'Introduction'
permalink: pt/overview/introduction.html
---

# Introduction

The UD collection currently contains two Portuguese treebanks: UD_Portuguese (a mixture of
European and Brazilian Portuguese) and UD_Portuguese-BR (Brazilian Portuguese).

## UD Portuguese

The UD Portuguese treebank is based on the Bosque part of the Floresta Sintá(c)tica project.
The data were used in the CoNLL-X Shared Task in dependency parsing (2006); the CoNLL version
was taken and converted to the Prague dependency style as a part of HamleDT (since 2011).
Later versions of HamleDT added a conversion to the Stanford dependencies (2014) and to
Universal Dependencies (HamleDT 3.0, 2015). The conversion path from the original Bosque still
goes through the CoNLL-X format and the Prague dependencies, which may occasionally lead to
loss of information. The first release of Universal Dependencies that includes this treebank
is UD v1.2 in November 2015. It is essentially the HamleDT conversion but the data is not
identical to HamleDT 3.0 because the conversion procedure has been further improved.

### Links

* [Floresta Sintá(c)tica](http://www.linguateca.pt/Floresta/principal.html)
* [HamleDT](http://ufal.mff.cuni.cz/hamledt)
* [Treex](http://ufal.mff.cuni.cz/treex) is the software used for conversion
* [Interset](http://ufal.mff.cuni.cz/interset) was used to convert POS tags and features

### References

* Susana Afonso, Eckhard Bick, Renato Haber, Diana Santos. 2002.
  [“Floresta sintá(c)tica”: a treebank for Portuguese](http://www.lrec-conf.org/proceedings/lrec2002/sumarios/1.htm).
  In: *Proceedings of the 3rd International Conference on Language Resources and Evaluation (LREC),* Las Palmas, Spain, pp. 1698-1703.

## UD Portuguese BR

The Portuguese-BR UD treebank comes from the universal Google dataset (version 2.0). It consists of text taken from newspaper articles, blogs and consumer reviews. The conversion to the UD POS and UD dependencies have been performed automatically, using heuristic rules and fixed lists of words. The output of the conversion has not been manually corrected.

More information about the original Google dataset can be found in the following paper:

  _Universal Dependency Annotation for Multilingual Parsing_
  Ryan McDonald, Joakim Nivre, Yvonne Quirmbach-Brundage, Yoav Goldberg,
  Dipanjan Das, Kuzman Ganchev, Keith Hall, Slav Petrov, Hao Zhang,
  Oscar Tackstrom, Claudia Bedini, Nuria Bertomeu Castello and Jungmee Lee
  Proceedings of ACL 2013
