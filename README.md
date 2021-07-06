# Ambiguity and Vagueness dictionaries
Marty Steer, Digital Humantities Research Hub (DHRH)
*School of Advanced Study, University of London*

Robert Hogenraad, Emeritus Professor (August 2017). Smoke and mirrors: Tracing ambiguity in texts. (Accessed 6 July 2021 from https://www.researchgate.net/publication/319136617_Smoke_and_mirrors_Tracing_ambiguity_in_texts)

*NB: I recieved a copy of the .lis files from a colleague in April 2018, and transformed them into CSV and JSONL versions for use in my own research projects.*The dictionary descriptions below are from the original PROTAN .lis files. Some hyperlinks have been fixed.

**Markers of ambiguity (polydlc.lis)**

Looking for markers of ambiguity, we selected from Empson's (1930) "Seven types of ambiguity" those types we could digitize into computer-readable format. Polysemy and contronyms were among those. We then looked at the following web sites and extracted the items marked as relevant to those two types of ambiguity:

1. https://www.dailywritingtips.com/75-contronyms-words-with-contradictory-meanings/
2. https://en.wiktionary.org/wiki/Appendix:Glossary_of_auto-antonyms
3. https://web.archive.org/web/20141129194141/http://www.huffingtonpost.com/marv-rubinstein/14-wacky-words-with-two-o_b_6213568.html
4. https://www.mentalfloss.com/article/49834/14-words-are-their-own-opposites



**The Vagueness Dictionary  (vagdlc.lis)**

The Vagueness Dictionary of words and short phrases was designed and alidated to detect when a communicator, writer or speaker, is "vague" in thought; when a communicator cannot recall a precise fact or idea that needs to be recalled, then an imprecise expression will be substituted to hurdle the gap. Furthermore, the communicator's self-awareness of having difficulty in recalling and expressing what was intended leads to verbalisms that cue that discomfort; the oft repeated "ya know" is precisely such a cue as the speaker attempts to shift the burden of what needs to be said to the listener to fill it in. Copyright (c) 1968. Jack H.Hiller



**The BOOSTERS Dictionary (boostdlc.lis)**

The BOOSTERS Dictionary of words and digrams was designed to collect a listof common entries (intensifiers) referring to any idea of commitment and solidarity with an audience or readership. Such words (sometimes digrams)are used also with the intention to manipulate a concensual understanding with readers or listeners. One expect boosters to runopposite to hedges. The latter refer to ideas of mitigating excessive expressions. The present dictionary is based on three studies:

1. Yagiz, O., & Demir, C. (2015). A comparative study of boosting in academic texts: A contrastive rhetoric. International Journal of English Linguistics, 5(4), 12-28. (Retrieved April 15, 2016 from https://www.ccsenet.org/journal/index.php/ijel/article/view/49346 or http://dx.doi.org/10.5539/ijel.v5n4p12
2. Peacock, M.(2006). A cross-disciplinary comparison of boosting in research articles. Corpora, 1(1), 61-84. [Retrieved April 18, 2016 from https://courses.washington.edu/englhtml/engl563/PDFs/Peacock.pdf or http://dx.doi.org/10.3366/cor.2006.1.1.61



### The categories

##### boostdlc CATEGORIES:

```
NUMBER  IDENTIFICATION                  WORDS  ROOTS  TOTAL
   OF CATEGORY                              FREQUENCIES
___________________________________________________________

   1    modal boosters                      3      0      3
   2    verbal boosters                     7      3     10
   3    adjectival/adverbial boosters       0     11     11
   4    Peacock list                       51     58    109
   5    varia                              13      0     13
```

##### polydlc CATEGORIES                                                              

```
01. CONTRONYMS=Two meanings into one word                                       
02. POLYSEMY=Multiple meanings.                                                 
02. TOTAL        
```

##### vagdlc CATEGORIES:

```
** VAGUE                                                                      **
NUMBER  IDENTIFICATION                  WORDS  ROOTS  TOTAL
   OF CATEGORY                              FREQUENCIES
___________________________________________________________

   1    ambiguous designation              52      0     52
   2    negated intensifiers               55      0     55
   3    approximation                      37      0     37
   4    bluff & recovery                   53      1     54
   5    admission of error                 20      0     20
   6    indefinite amount                  36      5     41
   7    multiplicity                       34      1     35
   8    probability & possibility          30      2     32
   9    reservations                       34      3     37
  10    anaphora                           14      0     14
```

#### Manual steps to transform .lis files to .csv

 These are the hacky manual steps were used to generate the csv files from the .lis files.

- regex extract from .lis files

  - find: `^.*?[0-9]+.+?[0-9]+\s(.*?)\s+.\s+([0-9]).*?$`

    replace: copy paste into new document.

- regex tidyup

  - find: `^.*?[0-9]+.+?[0-9]+\s(.*?)\s+.\s+([0-9]).*?$`

    replace: `$1,$2`

- find/replace digits for boost categories to tidy up further.

* then find/replace lines with plurality to make them individual entires
  * find: `^(.*?)\.\((.*),(.*$)`
    replace: `$1,$3\n$1$2,$3`

* manually correct terms ending in 'e'

* find/replace underscore with space:
  * find: `_`
    replace: `\s`
* find/replace to tidy up:
  * Find: `([a-z])\.\(([a-z])`
    Replace: `$1$2`

Now this text file can be used for downstream analysis combine/apply tasks.



MS, 2021-07