# BibleWorks to Unicode

Converts Bible Works Font Text ``a;nqrwpoj`` to real Greek characters ``ἄνθρωπος``.

This allows you to modernise how your text is stored/displayed and support things like Copy/Paste.


## Get started

This is a project template using [Vite](https://vitejs.dev/). It requires [Node.js](https://nodejs.org) v12+.

To start:

```sh
npm install
npm run dev
```

## Why?
A long time ago, to display Greek/Hebrew or other non-latin characters, you would write latin characters and change the font to make it look like the character you want.

The issue is that this method requires the user to have the font installed.

Another issue is that if you copied the letters from one application to another, you'd end up with ``a;nqrwpoj`` instead of ``ἄνθρωπος``. 

The modern way is to actually use the Unicode characters for the letters you want.

This app searches for character combinations and replaces with the corresponding greek letters based on what character BibleWorks would display.

For example:
* a > α
* b > β
* c > χ
* a' > ἂ
* e` > ἑ
* e' > ἒ
* i; > ἴ
* av| > ᾀ
* hv| > ᾐ

## Background
I am currently working for a publisher converting old books into eBooks. Greek and Hebrew text are using BibleWorks fonts making the book not display correctly.

To save the editors time, I created this time for the conversions.

I have no background in Greek/Hebrew, so I naïvely find a list of Greek characters and tried to find a similar character in the BibleWorks Font. 

## Contribute
If you would like to contribute:

1. Bugs/optimisations in software
2. Corrections to font conversions/translation
3. New fonts (I need to work on BibleWorks Hebrew soon but I'd be open to including non-Bibleworks fonts which act in a similar way) 

I'd be delighted if you submit a pull request!