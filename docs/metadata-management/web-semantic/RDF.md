# Introduction of RDF

**RDF (Resource Description Framework)** is a foundational component of the 
`semantic web and linked data ecosystems`. It is a standard developed by the `W3C (World Wide Web Consortium)` to 
support structured `data sharing` across domains and systems.


## Key concepts

RDF data is expressed in the form of `triples`:
- subject
- predicate
- object

Below is an example:

```shell
<http://example.com/book1> <dc:title> "A Brief History of Time"
```
> This says: the resource identified as book1 has the title “A Brief History of Time.”

### URIs

All `subjects, predicates`, and often `objects` are represented using URIs, ensuring global uniqueness.

### Serialization formats

RDF can be written in multiple syntaxes:
- Turtle (e.g., .ttl)
- RDF/XML
- N-Triples
- JSON-LD

RDF decouples data from applications and provides a flexible way to express relationships between data across systems.


