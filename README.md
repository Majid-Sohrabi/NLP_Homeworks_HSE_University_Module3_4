# NLP_Homeworks_HSE_University_Module3_4

This assignment is contains three tasks:

   1) Write a function which picks rhymes for a word using CMU Pronouncing Dictionary (nltk.corpus.cmudict). Two words usually rhyme if their pronunciation from the stressed syllable till the end of the word is the same.
   
   
   2) Improve our text generator using trigrams (nltk.trigram) instead of bigrams. The idea is to select the next word based on two previous words, not just one. It is acceptable if you have to start the generation from two initial words instead of one. Apply the generator to texts from different corpora.
   
   
   3) Write a code for Hangman game (https://en.wikipedia.org/wiki/Hangman_(game)). The code should select a random word from a dictionary (e. g. nltk.corpus.words) and show it to the user, replacing letters with dots. The user has to guess the word, naming one letter per move. If the named letter is there within the word, then all its occurrences are shown, otherwise the user loses an attempt. The user wins if (s)he opens all the letters before all attempts are spent, otherwise (s)he fails. You do not have to draw the hangman, just count the attempts left.
