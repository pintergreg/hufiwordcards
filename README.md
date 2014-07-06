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

I found that MidletPascal 3.x has problems with charachter encoding, so I was unable to display Hungarian (and Finnsh) accents if I write them into the source code.
But I managed to determine that if I use chr() function with proper values I can force the compilet to display them. So, I wrote a not too nice function to solve my problem with replacements.
The drawback of this method is its uglyness: I have to store words in database without accents, so I store them with numbers instead. The following table shows my 'solution'.

|character|code in db|value to replace|
|:-------:|:--------:|:--------------:|
|ö        |1         |246             |
|ü        |2         |252             |
|ó        |3         |243             |
|ő        |4         |244             |
|ú        |5         |250             |
|é        |6         |233             |
|á        |7         |225             |
|ű        |8         |251             |
|í        |9         |237             |
|ä        |0         |228             |

Fortunately, I need ten characters (I don't need capitals), and my function:

<pre><code>function encodeText(w:string):string;
var i:integer;
begin
  for i:=0 to length(w) do
  begin
    if (getChar(w,i)='1') then w:=setChar(w,chr(246),i);
    if (getChar(w,i)='2') then w:=setChar(w,chr(252),i);
    if (getChar(w,i)='3') then w:=setChar(w,chr(243),i);
    if (getChar(w,i)='4') then w:=setChar(w,chr(244),i);
    if (getChar(w,i)='5') then w:=setChar(w,chr(250),i);
    if (getChar(w,i)='6') then w:=setChar(w,chr(233),i);
    if (getChar(w,i)='7') then w:=setChar(w,chr(225),i);
    if (getChar(w,i)='8') then w:=setChar(w,chr(251),i);
    if (getChar(w,i)='9') then w:=setChar(w,chr(237),i);
    if (getChar(w,i)='0') then w:=setChar(w,chr(228),i);
  end;
  encodeText:=w;
end;
</code></pre>

Versions
========
Originally this project was not version controlled by git, so I created this repo subsequently and tracking is not too punctual.

Version has a X.Y.Z format and changesd according to the following rules:

* X+1 if new feature is added
* Y+1 if database growned or minor changes occured
* Z+1 if bug(s) fixed

Changes
=======

### 2.2.1
* card position bug fixed
* card option screen graphical bug fixed 

### 2.2
* wrong screen from now on shows the correct answer
* changed batch size to 42 (from 84)
* added another 42 words (now 462 words in db)
* added card position label to card screen

### 2.1
* added another batch of words (now 420 words in db)
* improved card drawing

### 2.0.2
* very annoying bug fixed; when batch (>1) was selected, the random card display wasn't' worked (infinty loop occured)

### 2.0.1
* graphical bugs fixed at card option screen (some part of drawing was static and optimised for the emulator, not my real phone)

### 2.0
* the 'main' feature added (word cards)

### 1.2
* added another batch (now 336 words in the database)

### 1.1
* added another batch (84 words) 
* 'end test' message now show when the 40-word test is over
* some bugs fixed 

### 1.0
* First release with 168 words, only function was the test, that gave a word from database, and 4 options (one correct) another 3 false ones. Task is to select the right one. 

<!--- https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet -->
