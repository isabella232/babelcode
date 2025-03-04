# Schema Parsing

One of the key components to BabelCode is the domain specific module we use to
represent the inputs and outputs of a given question. This module contains all
of the code to implement that functionality.

## [SchemaType](schema_type.py)

This is the core data structure of the domain specific language. This module has
both the implementation of the `SchemaType` class and helper functions.

The grammar of the domain specific language is as follows:
```
S  => LeafTypes | ListType | MapType
ListType => list<S> | set<CoreTypes>
MapType => map<CoreTypes;S>
LeafTypes => CoreTypes | "boolean" | "double" | "float" | "long"
CoreTypes => "character" | "integer" | "string"
```

## [Parsing](parsing.py)

This module contains all functions related to parsing schemas from the raw
dictionaries, as well as the functionality to convert the generic schema to a
language specific one.
