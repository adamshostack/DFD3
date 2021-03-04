# DFD3
Data flow diagrams, also called DFDs or threat modeling diagrams.

## Goal
Many people have presented various different ways to craft data flow diagrams over the years.  This is an attempt to both be precise about what this definition of a "v3 DFD" is, and also to encourage people to think about diagramming techniques themselves as something that, like code, can be specified and evolved over time, and labeled with a version.

### Symbols/Elements used

| Element | Symbol | Discussion |
|---------|--------|------------|
| External entity|  <img src ="icons/rectangle.png" width=50 height=50> | A sharp-cornered rectangle. Anything outside your control.  Examples include people and systems run by other organizations or even divisions.  For example, Joe's mobile phone, the Mint data aggregators (assuming you're modeling from a bank's perspective).  If you're modeling Mint, then the bank's systems would be external entities. 
| Process| <img src ="icons/rounded-rectangle.png" width=50 height=50> | A rounded rectangle.  Any running code, including compiled, scripts, shell commands, SQL stored procedures, et cetera.
| Data store|  <img src ="icons/cylinder-256.png" width=50 height=50> | A drum. Anywhere data is stored, including files, databases, shared memory, S3, cookies, et cetera.
| Data flows| <img src ="icons/arrow.png" width=50 height=50> | An arrow. All the ways that processes can talk to data stores or each other.
| Trust boundary | . . . | A closed shape drawn with a dashed or dotted line to denote difference realms of the level of trust. Usually a box.



## Definition
1. A V3 DFD uses 5 symbols.  A rectangle represents an external entity, a person or code outside your control.  A rounded rectangle represents a process. They're connected by arrows, which can be single or double headed.  Data stores are represented by parallel lines.  A trust boundary is a closed shape, usually a box.  All lines are solid, except those used for trust boundaries, which are dashed or dotted.  (There is no "multi-process" symbol in DFD3.)
2. It must not* depend on the use of color, but can use color for additional information.
3. All elements should have a label.
4. You may have a context diagram if the system is complex.  One is not required.
</ol>
* Must, must not, should, should not are used per IETF norms.



# Rationales

## Rounded rectangles
Are more space-efficient in a large diagram than circles.

## Boxed boundaries
Clearly show what's inside, in a way that arcs often fail to do. Dashes and dots are clearly different from other elements and reproduce clearly with black and white printers.

## Double headed arrows
Are easier to draw.  They don't show initiation of a connection, which is sad, and that can be shown with one arrowhead filled, the other open.

## No "Complex Processes"
Some approaches refer to complex processes, indicated by a doubled (concentric) circle. When to use them was never made clear, and so they're a bit of a distraction and I recommend against them.

## History and Relationships
I'm told that Gane and Sarson also used rounded rectangles long before me.  (Gane, Chris; Sarson, Trish. *Structured Systems Analysis: Tools and Techniques*, 1979.).  According to Richard Botting's CS372 [course notes](http://www.csci.csusb.edu/dick/cs372/a4.html) Yourdon and De Marco also used sharp rectangles for external entities.
