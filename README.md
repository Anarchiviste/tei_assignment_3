# TEI ODD stylesheet for anglo-saxon fanzine encoding.

Here is the link to my two previous assignment.
- https://github.com/Anarchiviste/evalXML.git
- https://github.com/Anarchiviste/TEI-assignment2.git

## Introduction

### IA statement
This time I used some generative IA to debug a problem with schematron.

### Previous iterations

The second iteration ended up with the use of workaround to counter somes limitation of base TEI. I was looking for a way of encoding the physicality of my documents. Some were handwritten, some printed, and all of them used complex craft between the text and de physicality to create sens (images, colors, techniques of printing).

Base tei encoding exemple :

```xml
<div1 n="5" rendition="#manuscript" rend="black_ink white_background">
  <p>Spread equality !</p>
  <div2>
    <figure>
      <figDesc>An A for anarchist, written in Gothic script, surrounded by a heart</figDesc>
    </figure>
  </div2>
</div1>
```

1) I created a external list with inside two entity, printed and manuscript, that was used to identify is a piece of text was printed or handwritten. As you can see, the @rendition attribute call the #manuscript value from an external file, and that is suboptimal. 

2) Another problem was the encoding of the "rest" of the physicality of my documents. Some used text written of surgical mask, colored paper. In my previous iteration, I just used the @rend attribute and parked here some description but I did not found sompething better.

### Current iteration and ODD customisation

Here is the new code for the same exemple :

```xml
<div1 n="5" rendition="manuscript" letter_color="black" material="paper" material_color="white">
  <p>Spread equality !</p>
  <div2>
    <figure>
      <figDesc>An A for anarchist, written in Gothic script, surrounded by a heart</figDesc>
    </figure>
  </div2>
</div1>
```
1) The @rendition attribute is still used, but now the manuscript and printed values are rules coded in the odd. As they are rules, there is no need for an external authority file, and the values set for @rendition is now closed only for this two values.

This rules for the div1 are optionnal because we sometime need a better granulosity in the description of the phyisicality than the page. This rules have been cloned for div2, p, titlePage, titlePart, docAuthor and docDate elements.

2) Other rules were written or modified :

- The zine encoding project choosed that 0 should be excluded from the value of @n
- As all zine encoded for this project are found online, msIdentifier must have a repository element and a idno element to identified the repository. We also force the use of the @source attribute inside the msIdentifier element. In the case that a source cannot be found, then the value no_repository should be used.
- We decided that the front page should use the titlePage element with docTitle and titlePart as descendant. The 1st titlePart element should always be the main part of the title, so this schematron rule verify that the @type of titlepart is equal to main.

