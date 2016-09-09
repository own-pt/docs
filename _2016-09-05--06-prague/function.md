---
layout: base
title:  'Function words in UD v2'
---

# Function words in UD v2

<!-- Background -->

## References 

#  https://github.com/UniversalDependencies/docs/issues/329
# http://universaldependencies.org/2015-08-23-uppsala/copula.html
# https://github.com/UniversalDependencies/docs/issues/256

## Copula constructions 

### Status quo

<!-- Some languages have very many copula verbs -->

* Languages are inconsistent with how they treat copula constructions. Some languages are very permissive with copula verbs (e.g. French has over 50 finite verbs with the `cop` relation).

<!-- Lasai nago | pozik nago -->

### Principles

* For copulas, we should be maximally restrictive with respect to which verbs can be copulas (only one verb in most languages) but maximally permissive when it comes to treating this verb as cop. Basically, the copula verb should never be the root, except through promotion (“he is not happy, but she is”). 
** That is: Any situation where we link a subject to "more information" should be considered copula 
** For languages where more copulas are used (e.g. Spanish, Basque, Catalan, Turkish, Kazakh), these are permitted, but only the copulas that are equivalent to English 'be'. That is, English "become" and Swedish "ble" are out.
* We need to give more detailed guidelines for choosing the predicate in copula sentences when it is not one of the obvious cases (noun, adjective). Idea: use obliqueness hierarchy.
* We may want to add the subtype `nsubj:cop` to avoid having to flip dependencies when the predicate is a clause. It may also be used more generally to signal that the subject in copula constructions is special.

<!-- Fran: -->

* We may want to be able to distinguish `nmod` when it attaches to clauses and when it attaches to nominals (e.g. "I am a teacher this morning", "I am a teacher in the university.")

### Examples and recommendation

#### Simple predication

People are generally happy with the copula being a dependent of the predicating 
element where it is a noun or an adjective. As mentioned in the documentation this improves 
crosslingual consistency. 

English: 
~~~ sdparse
She is a student .
~~~ 

Russian:
~~~ sdparse
Она студент . \n She student .
~~~ 

Turkish (and Turkic):
~~~ sdparse
O öğrenci . \n She student .
~~~ 

Finnish (and Balto-Finnic, Samic):
~~~ sdparse
Se on opiskelija . 
~~~

Spanish (and other Romance):
~~~ sdparse
Ella és estudiant .
~~~

Basque:
~~~ sdparse 
Ainhoa ikaslea da .
~~~

It also improves intra-language consistency, as can be seen if we put the example 
into the past tense. In both Russian and Turkish the structure remains the same, but 
would be different if we had the copula verb as the head.

English:
~~~ sdparse
She was a student .
~~~ 

Russian:
~~~ sdparse
Она была студент .
~~~ 

Turkish (and Turkic):
~~~ sdparse
O öğrenci -di .
~~~ 

Finnish (and Balto-Finnic, Samic):
~~~ sdparse
Se oli opiskelija . 
~~~

Spanish (and other Romance):
~~~ sdparse
Ella fue estudiante .
~~~

Note also that in Turkish (and other Turkic languages) the copula verb can alternate 
between tenses, here the future is expressed with ol- instead of i-:

~~~ sdparse
O öğrenci olacak . \n She student will.be .
~~~

There may be other alternations, for example between state and essence:

Spanish:
~~~ sdparse 
Ella es buena . \n She is good .
~~~ 

~~~ sdparse
Ella está buena . \n She is attractive .
~~~

Or: 

Basque:
~~~ sdparse 
Ni ikaslea naiz . \n I student am .
~~~

~~~ sdparse 
Ni pozik nago . \n I happy am .
~~~

A similar thing can happen in Swedish:

~~~ sdparse
Men jag är bara 21 och du blev 23 . \n But I am only 21 and you were 23 .
~~~
<!-- FMT: Check, is 'blev' here "were" or "had become" -->

#### Predication with attributive-like NPs

People are also generally happy with using the same structure for prepositional phrases that have some kind 
of non-compositional attributive-like meaning:

English:
~~~ sdparse
She is in great shape . 
~~~

~~~ sdparse
She is really on the ball with this .
~~~

Spanish:
~~~ sdparse
Esa canción está de puta madre . 
~~~

#### Adverbials: time and location

Having the copula as a head was slightly less accepted for constructions where there is some kind of compositional prepositional phrase or adverbial.

Issues with this analysis are:
* Which adverbial should become the head in expressions with more than one adverbial ?
** Should we make a technical decision and simply choose the first (or last?)

~~~ sdparse 
She is here . 
~~~ 

~~~ sdparse 
Hemen dago .
~~~
 
~~~ sdparse
She is in Prague with her friends . 
~~~

~~~ sdparse 
I am on my way . 
~~~

~~~ sdparse
Она в Праге с друзьями .
~~~

~~~ sdparse
O arkadaşıla Pragada .
~~~

~~~ sdparse
Se on Pragassa kaverinkaa . 
~~~

~~~ sdparse
Ella és a Praga amb els amics . 
~~~

~~~ sdparse
She was in Prague with her friends . 
~~~

~~~ sdparse
Она была в Праге с друзьями .
~~~

~~~ sdparse
O arkadaşıla Pragada -dı .
~~~

~~~ sdparse
Ella estava a Praga amb els amics . 
~~~

~~~ sdparse
Se oli Pragassa kaverinkaa . 
~~~

~~~ sdparse
The gods were not with us on that one . 
~~~ 

~~~ sdparse
She walked in and was out of there in 10 minutes . 
~~~

~~~ sdparse 
Det var i förrgår när jag stod och väntade på dig .
~~~

~~~ sdparse 
Dom ställena du gick till, det är dit jag brukar gå .
~~~

#### Existential constructions 

Currently, existential constructions have a special structure in English:

~~~ sdparse
There is a book on the table .
~~~

We suggest replacing this with:

....

~~~ sdparse
Есть книга в столе .
~~~

~~~ sdparse
Была книга в столе .
~~~

However, this quickly becomes awkward:

~~~ sdparse
For the last few years there have been problems with the programme .
~~~

~~~ sdparse 
How long have there been problems with the programme ? 
~~~

~~~ sdparse
Have there been problems with the programme for the last few years ? 
~~~

~~~ sdparse
What has there been with the programme for the last few years ? 
~~~

~~~ sdparse
There is a lot to learn about Chernobyl . 
~~~

There is no problem however for Turkic languages, where existential constructions are similar to simple predication with an adjective like var "existing", and yok "not.existing" .

~~~ sdparse
Masada kitap var . 
~~~

~~~ sdparse
Masada kitap var -dı . 
~~~

There is also no problem for Romance languages where a different structure is used:

~~~ sdparse
Hay un libro en la mesa . 
~~~

And Serbo-Croatian: 

~~~ sdparse 
Međutim , ima i dobrih vesti . \n But, have too good news .
~~~

This also goes for Scandinavian languages:

~~~ sdparse
Hur många invandrare finns det i Sverige ?
~~~

#### Clausal arguments

~~~ sdparse 
Being well-informed will give you certainty .
~~~

~~~ sdparse 
To be free is to be capable of thinking one's own thoughts .
~~~ 

~~~ sdparse 
The main thing is that the device works . 
~~~

~~~ sdparse
Трудно быть богом . 
~~~

~~~ sdparse 
Två viktiga ting är att säga om svårigheter i äktenskap .
~~~

~~~ sdparse 
En nödvändig förutsättning är att männen är helt med på saken
~~~

#### Ambiguities with auxiliary verbs

The following uses should not be considered copula.

~~~
I am reading these examples . 
~~~

~~~
The following criteria are considered .
~~~

~~~
Книга была прочитанно . 
~~~

~~~
El consumo de carne humano es considerado aceptable .
~~~

~~~
Det är skrivet till mig själv .
~~~

#### Other types 

~~~ sdparse 
This period in Athens, between 335 and 400 , is when Aristotle is believed to have lived .
~~~

#### Imperatives 

~~~ 
Be quiet ! 
~~~

#### Idiomatic expressions 

~~~ sdparse
Let there be light ! 
~~~

~~~ sdparse
I have been to Prague .
~~~

## Other functional relations

* The other functional relations are less problematic, but more detailed guidelines will be useful.