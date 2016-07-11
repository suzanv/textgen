# textgen
Script for generating text in the style of the oeuvre that is added as argument (in plain text).

Steps that the script takes:

A. Train on text:
 1. split in sentences (use list of abbreviations used in corpus)
 2. save sentence-initial and sentence-final words separately
 3. split the text in words, save all sequences of 2 words + 1 word (bigram model), and of 1 word + 1 word (unigram model)

B. Generate new text:
 1. each new paragraph starts with a word that occurs as begin-of-sentence in the training text
 2. start generating sentences until the minimum paragraph length has reached
 3. the start of a sentence is a random word based on the last two words of the previous sentence.
 4. words are generated randomly using the previous two words in the sentence (bigram model). If those do not exist in the style dictionary, use only the previous word (unigram model).
 5. words are generated until a sentence ending is encountered.

Minimal paragraph length and number of paragraphs are user-defined in the script (TODO: redefine as arguments)

The output is printed to inputfile.random[0-9]+
