# Analyse Language 

## Key topics 
'He stepped out into the hell, was delighted to encounter a water brother.'
- words: 
    - with punch: 15
    - without punch: 13
- types - 13 without punch 
- tokens - 13 without punch 
1. Definition and example of 
- Corpus: a computer-readable collection of text or speech. 
- Token: token are all the individual words including repeats. total number of N running words. 
- Type: Unique words in the corpus. 
- word: all the words in the corpus (with or without the punctuation depending on the task.)
- punctuation is useful to identify meaning, use for work separation and speech synthesis 
- sub-word: part/fragment of a word. To deal with unknown word problem, modern tokenizers often automatically induce sets of tokens that include tokens smaller than words. 
- lemma: A lemma is a set of lexical forms having the same stem. e.g. cats and cat have same lemma cat fut are different word forms. 
- morpheme: A morpheme is the smallest meaning bearing unit of a language. for examples the word unlikeliest has the morphemes un-, likely, and -est.
- POS-tag: is the process of assigning a part-of-speech to each word in a text. 
- name entity: proper names 
- content word: 
- function word: Closed class words are generally function words. Function words are short, occur frequently and often have structuring uses in grammar like it and or you

2. Differences between two terms 

3. functionality of the below analysis:
- normalization: cleaning the text by removing layout (para, underline, bold, markup, replace emojis and urls, replace numbers.  
- segmentation : segment based on sentence boundaries. 
    - word segmentation: for japanese and thai the character is too small a unit, and so algorithm for word segmentation is required. 
- tokenization: The task of segmenting running text into words. 
- byte-par encoding: The BPE token learning begins with vocabulary that is just the set of all individual characters. It then examines the training corpus, choose the two symbols that are most frequently adjacent. It continues to count and merge, creating new longer and longer character stings. unit k mergers have been done creating k novel token. 
- lemmatization: Lemmatization is the task of determining the two words have the same root, despite their surface difference. The world am, are and is have the shared lemma be. 
- Morphology: is the study of the way words are build up form smaller meaning-bearing units called morphemes. 
    - stems: the central morpheme of the word, supplying the main meaning. 
    - affixes: adding 'additional' meaning of various kinds. 
    - Steaming: the naive morphological analysis is called steaming. 
- POS-tagging: Taking a sequence of words and assigning each word a part of speech.
- named entity recognition 

4. difference between 17 word classes universal part-of-speech tags
- Open Class: continually being created or borrowed.  
    1. NOUN: Word for person, place, things - algorithm, cat, mango, beauty
    2. PROPN: Proper noun, name of a person, org, place etc - New York, David 
    3. ADJ: Noun modifiers describing properties - red, young, awesome 
    4. VERB: words for actions and processes - draw, provide, go
    5. ADV: verb modifiers of time, place, manner - very, slow, home, yesterday
    6. INTJ: interjection: exclamation, greeting, yes/no response etc. - oh,um, yes
- Closed Class: relatively fixed membership 
    7. ADP: Adposition (pre/post position) make's noun spacial, temporal - in, on, by, under.
    8. AUX: Auxiliary helping verbs making tense, aspect, mood - can, may, should,are
    9. CCONJ: Conjunction joins two phrases/clauses - and, or, but
    10. DET: determiner: marks noun phrase properties - a, an the, this
    11. NUM: numerical 
    12. PART: Particle, a preposition like form used together with a verb - up, down, on off
    13. PRON: pronoun, a shorthand for referring to an entity or event - he, she, this, that
    14. SCONJ: Subordinating Conjunction: joins a main clause with a subordinate clause such as a sentential complement - that, which
    15. PUNC: Punctuation
    16. SYM: symbols like $ or emoji
    17. X: other
- Others

5. determine the part-of-speech tag for a word is a given context 
- Parts of speech: POS and name entities aer useful clues to sentence structure and meaning. 
    - Noun: Nouns are words for peole, place or things 
        - Proper Noun: often an entire multi word phrase 
    - Pronoun: 
    - Verb:  
    - Preposition
    - Adverb
    - Conjunction: 
    - Participle
    - Article. 
6. Concept of ambiguity in par-of speech tagging
- tagging is a disambiguation task; word are ambiguous - have more than one possible part-of-speech and the goal is to find the correct tag for the situation. 
- 55%-67% of word tokens in running text are ambiguous. 
- baseline: given an ambiguous word, choose the tag which is most frequent in the training corpus. Most frequent tag baseline has an accuracy of about 92%.
7. Different named entity classes 
- Named Entity: is anything that can be referred to with a proper name: a person, a location, an organization. 
- Named entity tagging: The task of named entity recognition is to find spans of text that constitute proper names and tag the types of the entity
- 4 entity tags are most common 
    1. PER: People, character - Turing is giant of computer science
    2. ORG: Organization, company, sports team 
    3. LOC: Location, region, Mountains 
    4. GPE: Geo political entity, countries, states

8. BIO tagging scheme: The standard approach to sequence labeling for span-recognition problem like NER is BIO tagging. This method allows to treat NER like word-by-word sequence labeling task, via tags that capture both the boundary and the name entity type.

9. NLP Shared task and example 

10. Bender rule: The practice of naming the language studied, the practice of asking, as a reviewer, which language were studied, or the practice of being skeptical of claims of language independence when only one test language was used. 

11. Choose a langue. Provide an example for a linguistic property in which the language different from English and how this could affect a NLP task. 

# Lecture sheets 
- **Represent input:** Represent language in a way that a computer cna process it. 
- **Generating output:** Process language in a way that is useful for humans  
- Computational modelling: Understanding language language structure and usage



# Text Standardization 
1. Text Normalization 
    - remove layout
    - remove/replace emojis and urls 
    - replace number with NUM
    - Anonymization 
word normalization: is the task of putting words/tokens in a standard format, choosing a single normal form for wards with multiple forms like USA and US or 
2. Case folding: another kind of normalization, mapping everything to lower case. 
3. Segmentation: Used for segmentign a text into sentence are punctuation, like periods, 

BenderRule: always mention which language is being used. 
Why English fails to represent all languages. 
- It's a spoken language and not a signed language. 

Reading Comprehension Questions. 
1. Tokenization and Lemmatization. 
- What is a corpus 
- What is the difference between a lemma and a word form?
- What is the difference between a type and a token?
- Given three example of language varieties?
- Why is it important to consider language varieties in an NLP system?
- What is tokenization?
- Provide and example for an NLP task where punctuation is highly relevant and one for which it could be ignored. 
- What is the difference between a subword and a morpheme?
- what are the respective amims of a token learned and a token segmenter?
- what does the "k" represent in th eBPE algorithm?
- What happens with the size of the vocabulary in a BPE algorithm?
- What is the goal of a word normalization? Can you think of an example of different word forms that should be normalized for a specific task?
- What is morphological parsing?
- What is lemmatization?
- What is the difference between stemming and lemmatization?
- What is the purpose of a cascade in the Porter Teammer?
- What is the challenge of sentence segmentation rearding the period character "." and how can it be addressed?
2. POS Tagging and NER
- Given three example words for each Universal POS tag.
- What is the difference between open and closed word classes?
- What is the difference between content and function words?
- What is the Penn Treebank tagset and how does it differ from the Universal POS tags?
- Provide and example of a word that can have different POS tags depending on the context. 
- What is POS-tagging and why is it useful?
- What is a majority baseline (also called "most frequent class baseline") in the context of POS tagging?
- Explain the task of Named Entity Recognition. For which NLP task is it important to extract the named entities?
- Name the most common NE tags and provide and example for each. 
- Explain the BIO scheme and how it is used in NER.    
- Why is POS-tagging challenging for morphologically rich languages?
2. Shared task:
- Provide examples of NLP tasks and illustrate how the performance varies across languages.  
- Choose a specific task. What is the input and what is the output of this task? What kind of linguistic knowledge might required for these tasks?
3. Multilingualism:
- What is a high-resource language and what is a low-resource language?
- Why is it important to include low-resource language when developing NLP application?
- Explain the Bender rule and what motivated its creation. 
- What are data statements and how can they help to address biases in NLP models?