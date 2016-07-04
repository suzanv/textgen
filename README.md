# textgen
 script for generating text in the style of the oevre that is added as argument (in plain text).

 Train on text:
 1. split in sentences (use list of abbreviations used in corpus)
 2. save sentence-initial and sentence-final words separately
 3. split the text in words, save all sequences of 2 words + 1 word (bigram model), and of 1 word + 1 word (unigram model)
 Generate new text:
 1. each new paragraph starts with a word that occurs as begin-of-sentence in the training text
 2. pick random word based on the previous two words. If those do not exist in the model, use only the previous word.
 3. a paragraph is at least 30 words.
 4. after 30 words, random words are generated until a sentence ending is encountered.

 minimal sentence length and number of paragraphs are user-defined in the script (TODO: redefine as arguments)

 the output is printed to inputfile.random[0-9]
