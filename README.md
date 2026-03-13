# smilint-precommit

Rudimentary `pre-commit` hooks that leverage smilint from the
[libsmi project](https://www.ibr.cs.tu-bs.de/projects/libsmi/).

### Installation

This integration requires pre-commit to function. See the
[installation directions](https://pre-commit.com/#install) for more details.

### Example Usage

```
---
repos:
  - repo: https://github.com/ngie-eign/pre-commit
    rev: 1.0.0
    hooks:
      - id: smilint
        # `files` is set to the following by default.
        files: ['*-MIB.txt', '*.mib', '*.my']
```

### The difficulty with `files`, `types`, and MIB files

![xkcd-927-aka-standards](https://imgs.xkcd.com/comics/standards_2x.png)

Despite SNMP consisting of and consuming a number of IETF RFCs and standards,
there isn't a single file extension or set of established file extensions that
can be leveraged to help determine whether a file is a MIB or another
alternative plaintext format.

Ergo, pathing specified via `files` will likely need to be adjusted to work in
some non-standard cases.
