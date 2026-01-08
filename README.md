# TEI ODD stylesheet for anglo-saxon fanzine encoding.

Here is the link to my two previous assignment.
- https://github.com/Anarchiviste/evalXML.git
- https://github.com/Anarchiviste/TEI-assignment2.git

## Introduction

### IA statement
This time I used some generative IA to debug a problem with schematron.

### Previous iterations

The second iteration of my work with fanzine resulted in using a workaround to overcome some limitations of the TEI standard. I was looking for a way to encode the materiality of my documents. Some were handwritten, others printed, and all used complex know-how between text and materiality to create meaning (images, colors, printing techniques).

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

1) I created an external list containing two entities, `printed` and `handwritten` to identify whether a text was printed or handwritten. As you can see, the `@rendition` attribute calls the `#manuscript` value of an external file, which is not optimal.

2) Another problem concerned encoding the "rest" of the materiality of my documents. Some used text written on a surgical mask, others on colored paper. In my previous version, I simply used the `@rend` attribute and added a description, but I haven't found a better solution.

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
1) The `@rendition` attribute is still used, but the values ​​`manuscript` and `printed` are now rules coded in ODD. Since these are rules, no external authority file is required, and the values ​​defined for `@rendition` are now limited to these two values. the `@rend` attribute now free for another use.

These rules for `div1` are optional, as it is sometimes necessary to have a more precise description of the physical appearance than of the page itself. These rules have been duplicated for the `div2`, `p`, `titlePage`, `titlePart`, `docAuthor`, and `docDate` elements.

2) Other rules were written or modified :
  
- The fanzine encoding project has decided to exclude the value 0 for the `@n` attribute.

- Since all the fanzines encoded for this project are available online, `msIdentifier` must include a `repository` element and an `idno` element to identify the repository. The use of the `@source` attribute is also mandatory in the `msIdentifier` element. If no source is found, the value `no_repository` is used.

- It was decided that the homepage would use the `titlePage` element with `docTitle` and `titlePart` as descendants. The first `titlePart` element must always correspond to the main part of the title; this Schematron rule therefore checks that `@type` of `titlepart` is equal to `main`.
- 
### Reflections on TEI encoding and ODD personalization in the face of the diversity of fanzines.

I limited this iteration to a few rules and a few new elements. I had considered adding a "technical" element to describe the printing or drawing technique, or a "style" element to encode the writing style. But I ultimately abandoned this idea, because the diversity of fanzines is immense and creativity overflowing; it is therefore impossible to add a rule or element for every type of creation. Furthermore, since we created an element for document physicality, the `@rend` element is now free and can therefore be used by encoders to add their own descriptions of what is relevant in a fanzine, in addition to what I already encode. Because the TEI is based on a common rule allowing everyone to interact with each other's work, and given the diversity of the fanzine world, too strict an approach to customizing the TEI could be problematic for some. That's why I refused to take a radical approach of removing all unnecessary elements and attributes. If it wasn't useful to me, it might be to someone studying fanzines from a different perspective.
