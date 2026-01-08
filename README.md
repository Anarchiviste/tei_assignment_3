# TEI Assignment III

Here is the link to my two previous assignment.
- https://github.com/Anarchiviste/evalXML.git
- https://github.com/Anarchiviste/TEI-assignment2.git

## Introduction

### IA statement
This time I used some generative IA to debug a problem with schematron.

### Assignment I and II

My assignment II ended up with the use of workaround to counter somes limitation of base TEI.

1) I created a external list with inside two entity, printed and manuscript, that was used to identify is a piece of text was printed or handwritten.

base tei encoding exemple
''' xml
<div1 n="5" rendition="#manuscript" rend="black_ink white_background">
                <p>Spread equality !</p>
                <div2>
                    <figure>
                        <figDesc>An A for anarchist, written in Gothic script, surrounded by a
                            heart</figDesc>
                    </figure>
                </div2>
            </div1>

'''
