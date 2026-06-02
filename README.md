<H3 ALIGN=RIGHT> DATE:<H3>

<H1 ALIGN=CENTER> Experiment-6: Implementation of Semantic Analysis </H1>

### Name: Yogavarma B
### Register Number: 2305002029

## Aim: 

To perform Parts of speech identification and Synonym using Natural Language Processing (NLP) techniques.

## Algorithm:

**Step-1:** Import the nltk library.

**Step-2:** Download the 'punkt', 'wordnet', and 'averaged_perceptron_tagger' resources.

**Step-3:** Accept user input for the text.

**Step-4:** Tokenize the input text into words using the word_tokenize function.

**Step-5:** Iterate through each word in the tokenized text.
-	 Perform part-of-speech tagging on the tokenized words using nltk.pos_tag.
-	 Print each word along with its corresponding part-of-speech tag.
-	 For each verb , iterate through its synsets (sets of synonyms) using wordnet.synsets(word).
-	 Extract synonyms and antonyms using lemma.name() and lemma.antonyms()[0].name() respectively.
-  Print the unique sets of synonyms and antonyms.

## Program:

```python
import nltk
#import wordnet
nltk.download( 'punkt' )
nltk.download('wordnet')
from nltk.tokenize import word_tokenize
nltk.download( 'averaged_perceptron_tagger' )
sentence=input ()
# Tokenize the sentence into words
words = word_tokenize(sentence)
# Identify the parts of speech for each word
pos_tags= nltk.pos_tag(words)
from nltk.corpus import wordnet

# Identify synonyms and antonyms for each word
synonyms =[]
antonyms =[]
for word in words:
	for syn in wordnet.synsets(word) :
		for lemma in syn.lemmas():
			synonyms . append (lemma . name( ) )
			if lemma . antonyms():
				antonyms . append ( lemma. antonyms ( ) [0] . name ( ) )
# Print the synonyms and antonyms
print ( "Synonyms : " ,set (synonyms) )
print ( "Antonyms : " ,set(antonyms) )
```
---

## Output:

```
Enter a sentence: Old men dislike hot summer
```

```
[('Old', 'NNP'), ('men', 'NNS'), ('dislike', 'VB'), ('hot', 'JJ'), ('summer', 'NN')]
```

```
Synonyms :  {'summer', 'one-time', 'previous', "gentleman's_gentleman", 'mankind', 'summertime', 'erstwhile', 'gentleman',
'blistering', 'live', 'honest-to-god', 'dislike', 'red-hot', 'Old', 'human_beings', 'disfavor', 'valet_de_chambre',
'raging', 'workforce', 'world', 'hands', 'former', 'Man', 'humanity', 'hot', 'military_personnel', 'homo', 'sometime',
'sure-enough', 'work_force', 'disapproval', 'human', 'men', 'serviceman', 'humankind', 'disfavour', 'adult_male', 'man',
'older', 'human_being', 'onetime', 'quondam', 'valet', 'piece', 'human_race', 'spicy', 'old', 'honest-to-goodness',
'manpower', 'military_man', 'Isle_of_Man', 'humans'}
```

```
Antonyms :  {'young', 'woman', 'new', 'liking', 'like', 'cold', 'civilian'}
```
---

## Result:
Thus ,the program to perform the Parts of Speech identification and Synonymis executed sucessfully.
