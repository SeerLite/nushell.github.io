---
title: load-env
categories: |
  filesystem
version: 0.90.0
filesystem: |
  Loads an environment update from a record.
usage: |
  Loads an environment update from a record.
feature: default
---
<!-- This file is automatically generated. Please edit the command in https://github.com/nushell/nushell instead. -->

# <code>{{ $frontmatter.title }}</code> for filesystem

<div class='command-title'>{{ $frontmatter.filesystem }}</div>

## Signature

```> load-env {flags} (update)```

## Parameters

 -  `update`: The record to use for updates.


## Input/output types:

| input   | output  |
| ------- | ------- |
| nothing | nothing |
| record  | nothing |
## Examples

Load variables from an input stream
```nu
> {NAME: ABE, AGE: UNKNOWN} | load-env; $env.NAME
ABE
```

Load variables from an argument
```nu
> load-env {NAME: ABE, AGE: UNKNOWN}; $env.NAME
ABE
```
