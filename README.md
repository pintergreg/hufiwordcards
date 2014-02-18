hufiwordcards
=============

Hungarian - Finnish word learning application for j2me (hobby project)

**available under MIT licence**

This project is written in MidletPascal (3.5) to JavaME (MIDP 2.0)

The source code is relatively poorly commented, but comments and naming is in English, though the application interface is in Hungarian (no internationalization is planned)


Database
========
My original idea was to 'digitialize' my paper-based word cards, that was made by me to learn Finnish words and for some reason I used 84-card batches. I did not change this, so I kept this logical separation, but not at storing. I use a very simple 'database' format.

Database is text file with the following format: 

* finnish word[, synonym]
* hungarian word[, synonym]
* finnish word[, synonym]
* hungarian word[, synonym]
* and so on...

There can be max. 2 expressions in a row with a meaning, separated by a comma and a space (algorithm uses this fact).

## Character coding

to be written

Versions
========
Originally this project was not version controlled by git, so I created this repo subsequently and tracking is not too punctual.

Version has a X.Y.Z format and changesd according to the following rules:

* X+1 if new feature is added
* Y+1 if database growned or minor changes occured
* Z+1 if bug(s) fixed

Changes
=======

### 2.0.2
* very annoying bug fixed; when batch (>1) was selected, the random card display wasn't' worked (infinty loop occured)

### 2.0.1
* graphical bugs fixed at card option screen (some part of drawing was static and optimised for the emulator, not my real phone)

### 2.0
* the 'main' feature added (word cards)

### 1.2
* added another batch (not 336 word in the database)

### 1.1
* added another batch (84 words) 
* 'end test' message now show when the 40-word test is over
* some bugs fixed 

### 1.0
* First release with 168 words, only function was the test, that gave a word from database, and 4 options (one correct) another 3 false ones. Task is to select the right one. 

<!--- https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet -->