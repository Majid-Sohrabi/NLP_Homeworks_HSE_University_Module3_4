# NLP_Homeworks_HSE_University_Module3_4

## [Homework 1](https://github.com/Majid-Sohrabi/NLP_Homeworks_HSE_University_Module3_4/blob/main/Homework_1/NLP_Homework1_HSE_Module3_4.ipynb) contains three tasks:

   1) Write a function which picks rhymes for a word using CMU Pronouncing Dictionary (nltk.corpus.cmudict). Two words usually rhyme if their pronunciation from the stressed syllable till the end of the word is the same.
   
   
   2) Improve our text generator using trigrams (nltk.trigram) instead of bigrams. The idea is to select the next word based on two previous words, not just one. It is acceptable if you have to start the generation from two initial words instead of one. Apply the generator to texts from different corpora.
   
   
   3) Write a code for Hangman game (https://en.wikipedia.org/wiki/Hangman_(game)). The code should select a random word from a dictionary (e. g. nltk.corpus.words) and show it to the user, replacing letters with dots. The user has to guess the word, naming one letter per move. If the named letter is there within the word, then all its occurrences are shown, otherwise the user loses an attempt. The user wins if (s)he opens all the letters before all attempts are spent, otherwise (s)he fails. You do not have to draw the hangman, just count the attempts left.


## [Homework 2](https://github.com/Majid-Sohrabi/NLP_Homeworks_HSE_University_Module3_4/blob/main/Homework_2/NLP_Homework2_HSE_Module3_4.ipynb)

   1) Build your own POS tagger for Russian training it on the disambiguated part of opencorpora corpus. You can choose from a number of methods described in chapters 5 and 6 of the book such as Unigram/Biggram Taggers, AffixTagger or NaiveBayes/DecisionTree/Maxent Classifiers. Try to achieve best performance analyzing errors that your tagger makes. Compare your performance with pymorphy2.

   opencorpora can be downloaded from here: http://opencorpora.org/?page=downloads

   opencorpora documentation: https://pypi.org/project/opencorpora-tools/0.3/

   pymorphy2 documentation: https://pymorphy2.readthedocs.io/en/latest/user/guide.html

   2) Build a named entity classifier for Spanish based on nltk.corpus.conll2002. You can take the code of ConsecutiveNPChunker from p. 3.3 of chapter 7 of the book as an example. Use 'esp.train' file for training, 'esp.testa' for debugging and 'esp.testb' for final testing.

   3) Collect the probabilistic grammar from Penn treebank corpus (nltk.corpus.treebank) using nltk.Tree.productions() method. Save the grammar to a file. Create a parser based on the grammar and try to parse some English sentences with it. If the parser fails because of missing words in the vocabulary, replace the words in the sentence with similar words of the same category. After that - does the parser create reasonably correct trees?

   Note: NLTK grammar does not allow punctuation marks in category labels and does not allow a category label to begin with a dash. So you have to modify category labels extracted from the treebank to match the rules of NLTK grammar.

   4) Write a function that generates a random sentence based on a given probabilistic grammar. You can use grammar.start() to identify the starting symbol of the grammar (normally S) and grammar.productions(lhs) to get all the productions with the same left hand side (lhs). Generate some sentences from the grammar collected in the previous task. Do they look reasonably grammatical?

   Based on your experiments with the grammar in tasks 3 and 4 - what are the strong and weak points of the collected grammar?
   
   
   ## [Homework 3](https://github.com/Majid-Sohrabi/NLP_Homeworks_HSE_University_Module3_4/blob/main/Homework_3/NLP_Homework3_HSE_Module3_4.ipynb)
   
   1) Translate into predicate logic:
Angus likes Cyril and Irene hates Cyril.
Bruce loves himself and Pat does too.
Cyril saw Bertie, but Angus didn't.
Cyril is a fourlegged friend.
Angus likes someone and someone likes Julia.
Angus loves a dog who loves him.
Nobody coughed or sneezed.
Cyril likes everyone except for Irene.

   2) Translate into lambda expressions over a predicate logic formulas:
feed Cyril and give a capuccino to Angus
be given a book by Pat
be loved or detested by everyone
be loved by everyone and detested by no-one

   3) For the following discourse create a grammar which translates the sentences into predicate logic. Manually create a model to check the truth of the resulting formulas. 
A black kitten saw a mouse. The kitten rushed after it.
The mouse jumped into a jar [of flour].
The kitten followed it.
The mouse ran away.
A white kitten got out of the jar.

You can omit the part in the square brackets if there is a problem with it. Treat the article 'the' as the quantifier 'exists unique'. The lambda expression for it would be \P Q.exists x.((P(x) & Q(x)) & all y.(P(y) -> (x = y))). If there is a problem with the pronoun 'it', you can replace it with the noun phrase 'the mouse' directly in the text and process the modified discourse.

Take the following grammar as an example:
nltk.data.show_cfg('grammars/book_grammars/discourse.fcfg')

   4) The same as in the previous task but instead of predicate logic formulas translate the sentences into DRSs. Treat the article 'the' the same way as 'a', but in addition mark the variable with PRO predicate to show that it requires resolution in the same way as pronouns. Combine all DRSs into one using '+' operation and manually add resolution for all PRO variables. I. e. add conditions of the form (x = y), where x is the variable marked with PRO and y is its antecedent (the object which the pronoun or the noun phrase refers to). You can add them by creating a separate DRS and combining it with the rest of DRSs using '+' operation. After that use simplify() to get one DRS as a result of 'addition', then eliminate_equality() to reduce the number of variables, the fol() to convert the resulting DRS into predicate logic and check the truth of the formula in your model. 

Take the following grammar as an example:
nltk.data.show_cfg('grammars/book_grammars/drt.fcfg')
