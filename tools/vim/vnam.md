# Verbs, Nouns and Modifiers

Talk to your vim editor in ‘verb modifier object’ sentences, turned into acronyms

### Verbs. The operation

* v (visual) 
* c (change) 
* d (delete) 
* y (yank/copy)

### Nouns. The object to operate
* w (word) 
* s (sentence) 
* p (paragraph) 
* b (block/parentheses) 
* t (tag, works for html/xml) xml,


### Modifiers. How to operate
* i (inside)
* a (around)*
* t (till..finds a character)
* f (find..like till except including the char)
* / (search..find a string/regex)

### Examples.
* delete the current word: diw (delete inside word)
* change current sentence: cis (change inside sentence)
* change a string inside quotes: ci” (change inside quote)
* change until next occurrence of ‘foo’: c/foo (change search foo)
* change everything from here to the letter X: ctX
* visually select this paragraph: vap (visual around paragraph)

* d/xml delete till the first found xml, xml is NOT included

### Key Notes.
* There are more verbs, nouns and modifiers, with plugins

## Reference
* https://yanpritzker.com/learn-to-speak-vim-verbs-nouns-and-modifiers-d7bfed1f6b2d
* book: `Practical Vim`
