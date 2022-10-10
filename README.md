# BibleWorks to Unicode

This online tool allows you to modernise how your text is stored/displayed and support textual features such as Copy/Paste, changing fonts etc.

This converts Bible Works Font Text ``a;nqrwpoj`` to real Greek characters ``ἄνθρωπος``. The encoding is UTF-8.

## Get Started (use the tool)

* Visit https://banneroftruth.github.io/BibleWorksToUnicode/
* Follow the instructions
* Step 3 shows a preview of your original BibleWorks text (requires the font to be installed).

## Get started (Development)

This is a project template using [Vite](https://vitejs.dev/). It requires [Node.js](https://nodejs.org) v12+.

To start:

```sh
npm install
npm run dev
```

## Why?
A long time ago, to display Greek/Hebrew or other non-Latin characters, you would write Latin characters and change the font to make it look like the character you want. This is how BibleWorks worked.

This leads to the following problems
* this method requires the user to have the font installed.
* Copying letters from one application to another, you'd end up with ``a;nqrwpoj`` instead of ``ἄνθρωπος``. 
* You can't search for specific greek characters using find/replace functions.

The modern way is to use Unicode characters for the letters you want. This allows you to change the font.

This app searches for character combinations and replaces them with the corresponding greek letters based on what character BibleWorks would have displayed.

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
I am currently working for a publisher converting old books into eBooks. Older titles use BibleWorks fonts and are not always displayed correctly.

To save the editors time, I created this tool for the conversions.

I have no background in Greek/Hebrew, so I have made an educated guess of the Unicode Greek characters and the similar character in the BibleWorks Font. 

## Contribute
If you would like to contribute:

1. Bugs/optimisations in software
2. Corrections to font conversions/translation
3. New fonts (I need to work on BibleWorks Hebrew soon but I'd be open to including non-Bibleworks fonts which act in a similar way) 

I'd be delighted if you submit a pull request!

## Helpful links

If you are contributing font conversions, please use the following sites:

**What Unicode character is this?**  
https://www.babelstone.co.uk/Unicode/whatisit.html

For example, some fonts display GREEK KORONIS `᾽` exactly the same as RIGHT SINGLE QUOTATION MARK `’`. Although they look the same, from a code point of view, it’s a different character. Copy and paste characters into the above website to confirm the character code is what you expect. Note: sometimes letters are not named correctly. You'll have to lookup guidance.

**Character lookups**  
https://www.compart.com/en/unicode/

Good for listing character sets.
