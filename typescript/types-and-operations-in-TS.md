# Types and Operations in TS type system

## types
TS supports all the JS types, like 
`number、boolean、string、bigint、symbol、undefined、null` 
and `object、array、class`. 

Other than that, TS added three new types(`Tuple, Interface, Enum`) and four special types(`never, void, any, unknown`)

In addition, TS also supports `literal type`, such as **'aa', 11, {a:1}**, even **aaa${string}**.

## type decoration
`readonly` and `?`

## operations
**Condition: `extends ? :` (similar to if else)**  
**Derivation: `infer`**  
**Union: `|`**  
**Intersection: `&`**  
**Mapping type(`keyof`)**  


