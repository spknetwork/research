# Validation module overview

## Module Responsibilities

1. Register/deregister schemas in ceramic using their Schema StreamID (i.e. a documentId or TileDocument)
2. Validate incoming datasets/subgraphs for authenticity against advertised Schema
3. Ask other nodes for subgraphs following only the requested schema.
4. Provide other nodes with subgraphs following the schema they request/supports
5. Small index of datasets/subgraphs by their schema. Quickly be able to find all datasets using schema X, Y and Z

For now store all schema registration info in memory or in mongodb.
Later we can move the schema registration to a data directory.
Subgraphs refers to the list of child entries of a root object
Datasets is used as a catch all term for any data being indexed by the node, subgraph or not.
I need to work on clarifying the terms better but this should give you a good idea on what this all looks like. The above will give you a good idea what to do then we can start dialing in and refining it from there.

Later on:

Divide subgraph communication by schema ID. (for now we should just add a tag on the subgraph metadata for differentiation, i dont know how relevant this is)
Build a way for applications to be notified of incoming data for their supported schema. Build abstractions from data with a specific schema.