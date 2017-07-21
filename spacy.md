
# SpaCy

Spacy is an open source platform available in Python for Natural Language Processing. Its speed, comprehensiveness, and thorough documentation make it a strong choice for both industry and academia. 

### install

```
pip3 install spacy
```

### import


```python
import spacy
```

### data
python3 -m spacy.en.download all

```python
x = spacy.load('en')
```

### languages


```python
parser = spacy.en.English()
```


```python
spacy.de.German()
```




    <spacy.de.German at 0x157666ba8>




```python
spacy.fr.French()
```




    <spacy.fr.French at 0x1eb8590b8>




```python
spacy.es.Spanish()
```




    <spacy.es.Spanish at 0x14b461a20>




```python
spacy.it.Italian()
```




    <spacy.it.Italian at 0x14b461f98>




```python
spacy.pt.Portuguese()
```




    <spacy.pt.Portuguese at 0x14b461b38>




```python
spacy.nl.Dutch()
```




    <spacy.nl.Dutch at 0x14b461ef0>




```python
spacy.sv.Swedish()
```




    <spacy.sv.Swedish at 0x13b89e978>




```python
spacy.fi.Finnish()
```




    <spacy.fi.Finnish at 0x13b89e828>




```python
spacy.hu.Hungarian()
```




    <spacy.hu.Hungarian at 0x13b89e6a0>




```python
spacy.bn.Bengali()
```




    <spacy.bn.Bengali at 0x13b89e7f0>




```python
spacy.he.Hebrew()
```




    <spacy.he.Hebrew at 0x13b89e550>




```python
spacy.zh.Chinese()
```




    <spacy.zh.Chinese at 0x13b89ee10>



### specific data


```python
parser.vocab['NASA']
parser.vocab['apple']
parser.vocab['UNK']
```




    <spacy.lexeme.Lexeme at 0x195764360>



### loading parent doc


```python
x = x("Hello, I like to program. My favorite language is Python.")
```

### parent doc type


```python
x[0].lang_
```




    'en'



### sentences


```python
for i in x.sents:
    print(i)
```

    Hello, I like to program.
    My favorite language is Python.


### lower


```python
x[0].orth_
```




    'Hello'




```python
x[0].lower_
```




    'hello'



### prefix


```python
x[0].prefix_
```




    'H'



### suffix


```python
x[0].suffix_
```




    'llo'



### shape


```python
x[0].shape_
```




    'Xxxxx'



### log probability


```python
x[0].prob
```




    -11.369197845458984



### sentiment


```python
x.sentiment
```




    0.0



### brown cluster ID


```python
x[0].cluster
```




    1726



### vectors


```python
king = x.vocab['king'].vector
```

### lemmatizing


```python
for i in x:
    print(i,":",i.lemma_)
```

    Hello : hello
    , : ,
    I : -PRON-
    like : like
    to : to
    program : program
    . : .
    My : -PRON-
    favorite : favorite
    language : language
    is : be
    Python : python
    . : .


### parts of speech


```python
for i in x:
    print(i,":",i.pos_)
```

    Hello : INTJ
    , : PUNCT
    I : PRON
    like : VERB
    to : PART
    program : VERB
    . : PUNCT
    My : ADJ
    favorite : ADJ
    language : NOUN
    is : VERB
    Python : PROPN
    . : PUNCT


### entity types


```python
x[0].ent_type
```




    0




```python
x[0].ent_iob_
```




    'O'



0 = no tag is assigned. <br>
1 = `I` = inside an entity. <br>
2 = `O` = no tag is assigned. <br>
3 = `B` = begins an entity.

### PoS string


```python
x[0].dep_
```




    'intj'



### entities


```python
for i in x.ents:
    print(i,i.label_)
```

    Python PERSON


### nounphrases


```python
for i in x.noun_chunks:
    print(i)
```

### similarity


```python
print(x[5],x[9])
x[5].similarity(x[9])
```

### dependency trees


```python
for i in x.sents:
    print(i.root)
    print(list(i.root.children))
```

### performance review

![spacy vs nltk image.png](attachment:image.png)

### matchers


```python
from spacy.matcher import Matcher
```


```python
x = spacy.load('en')
matcher = Matcher(x.vocab)
```

### entities


```python
matcher.add_entity(
    "GoogleNow",
)
```


```python

```



### patterns


```python
from spacy.attrs import ORTH
```


```python
matcher.has_entity(LOWER)
```


```python
matcher.add_pattern(
    "GoogleNow", 
    [{ORTH: "Google"},
    {ORTH: "Now"}],
    label=None
)
```

### third party modules

sense2vec <br>
displaCy <br>
textacy <br>
spacyr <br>


```python

```
