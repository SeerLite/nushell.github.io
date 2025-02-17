---
title: from vcf
categories: |
  formats
version: 0.90.0
formats: |
  Parse text as .vcf and create table.
usage: |
  Parse text as .vcf and create table.
feature: default
---
<!-- This file is automatically generated. Please edit the command in https://github.com/nushell/nushell instead. -->

# <code>{{ $frontmatter.title }}</code> for formats

<div class='command-title'>{{ $frontmatter.formats }}</div>


::: warning
Command `from vcf` resides in [plugin](/book/plugins.html) [`nu_plugin_formats`](https://crates.io/crates/nu_plugin_formats). To use this command, you must install/compile and register nu_plugin_formats
:::
## Signature

```> from vcf {flags} ```


## Input/output types:

| input  | output |
| ------ | ------ |
| string | table  |

## Examples

Converts ics formatted string to table
```nu
> 'BEGIN:VCARD
N:Foo
FN:Bar
EMAIL:foo@bar.com
END:VCARD' | from vcf
╭───┬──────────────────────────────────────╮
│ # │              properties              │
├───┼──────────────────────────────────────┤
│ 0 │ ╭───┬───────┬─────────────┬────────╮ │
│   │ │ # │ name  │    value    │ params │ │
│   │ ├───┼───────┼─────────────┼────────┤ │
│   │ │ 0 │ N     │ Foo         │        │ │
│   │ │ 1 │ FN    │ Bar         │        │ │
│   │ │ 2 │ EMAIL │ foo@bar.com │        │ │
│   │ ╰───┴───────┴─────────────┴────────╯ │
╰───┴──────────────────────────────────────╯

```
