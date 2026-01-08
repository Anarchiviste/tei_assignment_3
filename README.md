# TEI ODD stylesheet for anglo-saxon fanzine encoding.

Here is the link to my two previous assignment.
- https://github.com/Anarchiviste/evalXML.git
- https://github.com/Anarchiviste/TEI-assignment2.git

## Introduction

### IA statement
This time I used some generative IA to debug a problem with schematron.
 
### Reflections on TEI encoding and ODD personalization in the face of the diversity of fanzines.

I limited this iteration to a few rules and a few new elements. I had considered adding a "technical" element to describe the printing or drawing technique, or a "style" element to encode the writing style. But I ultimately abandoned this idea, because the diversity of fanzines is immense and creativity overflowing; it is therefore impossible to add a rule or element for every type of creation. Furthermore, since we created an element for document physicality, the `@rend` element is now free and can therefore be used by encoders to add their own descriptions of what is relevant in a fanzine, in addition to what I already encode. Because the TEI is based on a common rule allowing everyone to interact with each other's work, and given the diversity of the fanzine world, too strict an approach to customizing the TEI could be problematic for some.  This reflexion guided me to not create a list of values for the `color` and `material` element. What if someone want to use a pip tool and encode the exact value of the hexcode of the color inside `color` ? That's why I refused to take a radical approach of removing all unnecessary elements and attributes. If it wasn't useful to me, it might be to someone studying fanzines from a different perspective.
