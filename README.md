# DFD3
Data flow diagrams, also called DFDs or threat modeling diagrams.

## Goal
Many people have presented various different ways to craft data flow diagrams over the years.  This is an attempt to both be precise about what this defninition of a "v3 DFD" is, and also to encourage people to think about diagramming techniques as something that, like code, can be specified and evolved over time.

## Definition
1. A V3 DFD uses 5 symbols.  A rectangle represents an external entity, a person or code outside your control.  A rounded rectangle represents a process. They're connected by arrows, which can be single or double headed.  Data stores are represented by parallel lines.  A trust boundary is a closed shape, usually a box.  All lines are solid, except those used for trust boundaries, which are dashed or dotted.  (There is no "multi-process" symbol in DFD3.)
2. It must not* depend on the use of color, but can use color for additional information.
3. All elements should have a label.
4. You may have a context diagram if the system is complex.  One is not required.
</ol>
* Must, must not, should, should not are used per IETF norms.

### Symbols/Elements used

* External entity: A sharp-cornered rectangle. Anything outside your control.  Examples include people and systems run by other organizations or even divisions.  For example, Joe's mobile phone, the Mint data aggregators (assuming you're modeling from a bank's perspective.).  If you're modeling Mint, then the bank's systems would be external entities.
* Process: <img src ="icons/rounded-rectangle.png" width=40 height=20>A rounded rectangle.  Any running code, including compiled, scripts, shell commands, SQL stored procedures, et cetera.
* Data store: A drum. Anywhere data is stored, including files, databases, shared memory, S3, cookies, et cetera.
* Data flows: All the ways that processes can talk to data stores or each other.



# Rationales

## Rounded rectangles
Are more space-efficient in a large diagram than circles.

## Boxed boundaries
Clearly show what's inside, in a way that arcs often fail to do.

## Double headed arrows
Are easier to draw.  They don't show initiation of a connection, which is sad, and that can be shown with one arrowhead filled, the other open.

## Notes
I'm told that Gane and Sarson also used rounded rectangles long before me.  (Gane, Chris; Sarson, Trish. *Structured Systems Analysis: Tools and Techniques*, 1979.)
