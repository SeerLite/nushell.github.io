---
title: parse
categories: |
  strings
version: 0.90.0
strings: |
  Parse columns from string data using a simple pattern.
usage: |
  Parse columns from string data using a simple pattern.
feature: default
---
<!-- This file is automatically generated. Please edit the command in https://github.com/nushell/nushell instead. -->

# <code>{{ $frontmatter.title }}</code> for strings

<div class='command-title'>{{ $frontmatter.strings }}</div>

## Signature

```> parse {flags} (pattern)```

## Flags

 -  `--regex, -r`: use full regex syntax for patterns

## Parameters

 -  `pattern`: The pattern to match.


## Input/output types:

| input     | output |
| --------- | ------ |
| list\<any\> | table  |
| string    | table  |
## Examples

Parse a string into two named columns
```nu
> "hi there" | parse "{foo} {bar}"
╭───┬─────┬───────╮
│ # │ foo │  bar  │
├───┼─────┼───────┤
│ 0 │ hi  │ there │
╰───┴─────┴───────╯

```

Parse a string using regex pattern
```nu
> "hi there" | parse --regex '(?P<foo>\w+) (?P<bar>\w+)'
╭───┬─────┬───────╮
│ # │ foo │  bar  │
├───┼─────┼───────┤
│ 0 │ hi  │ there │
╰───┴─────┴───────╯

```

Parse a string using fancy-regex named capture group pattern
```nu
> "foo bar." | parse --regex '\s*(?<name>\w+)(?=\.)'
╭───┬──────╮
│ # │ name │
├───┼──────┤
│ 0 │ bar  │
╰───┴──────╯

```

Parse a string using fancy-regex capture group pattern
```nu
> "foo! bar." | parse --regex '(\w+)(?=\.)|(\w+)(?=!)'
╭───┬──────────┬──────────╮
│ # │ capture0 │ capture1 │
├───┼──────────┼──────────┤
│ 0 │          │ foo      │
│ 1 │ bar      │          │
╰───┴──────────┴──────────╯

```

Parse a string using fancy-regex look behind pattern
```nu
> " @another(foo bar)   " | parse --regex '\s*(?<=[() ])(@\w+)(\([^)]*\))?\s*'
╭───┬──────────┬───────────╮
│ # │ capture0 │ capture1  │
├───┼──────────┼───────────┤
│ 0 │ @another │ (foo bar) │
╰───┴──────────┴───────────╯

```

Parse a string using fancy-regex look ahead atomic group pattern
```nu
> "abcd" | parse --regex '^a(bc(?=d)|b)cd$'
╭───┬──────────╮
│ # │ capture0 │
├───┼──────────┤
│ 0 │ b        │
╰───┴──────────╯

```
