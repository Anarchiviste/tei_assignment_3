# TEI Assignment III

Here is the link to my two previous assignment.
- https://github.com/Anarchiviste/evalXML.git
- https://github.com/Anarchiviste/TEI-assignment2.git

## Introduction

### IA statement
This time I used some generative IA to debug a problem with schematron.

### Assignment I and II

My assignment II ended up with the use of workaround to counter somes limitation of base TEI. I was looking for a way of encoding the physicality of my documents. Some were handwritten, some printed, and all of them used complex craft between the text and de physicality to create sens (images, colors, techniques of printing).

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

2) Another problem was the encoding of the "rest" of the physicality of my documents. Some used text written of surgical mask, colored paper. In my assignement II, I just used the @rend attribute and parked here some description but I did not found sompething better.

### Assignment III and ODD customisation

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
