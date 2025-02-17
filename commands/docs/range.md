---
title: range
categories: |
  filters
version: 0.90.0
filters: |
  Return only the selected rows.
usage: |
  Return only the selected rows.
feature: default
---
<!-- This file is automatically generated. Please edit the command in https://github.com/nushell/nushell instead. -->

# <code>{{ $frontmatter.title }}</code> for filters

<div class='command-title'>{{ $frontmatter.filters }}</div>

## Signature

```> range {flags} (rows)```

## Parameters

 -  `rows`: Range of rows to return.


## Input/output types:

| input     | output    |
| --------- | --------- |
| list\<any\> | list\<any\> |

## Examples

Get the last 2 items
```nu
> [0,1,2,3,4,5] | range 4..5
╭───┬───╮
│ 0 │ 4 │
│ 1 │ 5 │
╰───┴───╯

```

Get the last 2 items
```nu
> [0,1,2,3,4,5] | range (-2)..
╭───┬───╮
│ 0 │ 4 │
│ 1 │ 5 │
╰───┴───╯

```

Get the next to last 2 items
```nu
> [0,1,2,3,4,5] | range (-3)..-2
╭───┬───╮
│ 0 │ 3 │
│ 1 │ 4 │
╰───┴───╯

```
