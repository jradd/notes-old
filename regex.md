# Regular Expressions
Bash

### Anchoring
`^` and `$` are meta-characters that respectively match empty string
at beginning and end of line.

### Char Classes
`[a-b]` in range 
`^[a-b]` *not* in range

### Bracket Expressions

`[:alnum:]` `[:alpha:]` `[:cntrl:]` `[:digit:]` `[:graph:]`
`[:lower:]` `[:print:]` `[:punct:]` `[:space:]` `[:upper:]`
`[:xdigit:]`

`[[:alnum:]]` ==> `[0-9A-Za-z]`


### Repitition
| Expression  | Representation       |     misc   |
| ----------- |:--------------------:|:----------:|
| `?`         | [?p <= 1]            | `{lte 1}`  |
| `*`         | [p <= 0]             | `{lte 0}`  |
| `+`         | [p >= 1]             | `{gte 1}`  |
| `{n}`       | [p = n]              | `{e}`      |
| `{n,}`      | [p >= n]             | `{gte,}`   |
| `{n,m}`     | [(p >= n), (p <= m)] | `{gte,lte}`|

### Concatenation
Two RE may be concatenated; resulting RE matches any string formed by
concatenating two substrings that respectively match the concatenated 
expression.

### Alternation
Join two REGEX by joining with the infix operator `|;`

##### Precedence
`Repitition` takes precedence over `concatenation` which in turn takes
precedence over `alternation`.

###### Basic VS Extended
Basic     --> escape expressions (eg; `\?`)
Extended  --> no need to escape
          `[{]` matches literal "{"
