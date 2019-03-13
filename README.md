# go-gitdiff

A Go library for parsing and applying patches generated by `git diff`, `git
show`, and `git format-patch`. It can also parse and apply unified diffs
generated by the standard `diff` tool.

## Status

In development, most functionality is currently missing, incomplete, or broken.

## Why another git/unified diff parser?

[Several][sourcegraph] [packages][sergi] with [similar][waigani]
[functionality][seletskiy] exist, so why did I write another?

1. No other packages I found support binary diffs, as generated with the
   `--binary` flag. This is the main reason for writing a new packages, as the
   format is pretty different from line-oriented diffs and is unique to Git.

2. Most other packages only parse patches, so you need another package to apply
   them (and if they do support applies, it is only for text files.)

3. This package aims to accept anything that `git apply` accepts, and closely
   follows the logic in [`apply.c`](https://github.com/git/git/blob/master/apply.c).

4. It seemed like a fun thing to write and a good way to learn more about Git.

[sourcegraph]: https://github.com/sourcegraph/go-diff
[sergi]: https://github.com/sergi/go-diff
[waigani]: https://github.com/waigani/diffparser
[seletskiy]: https://github.com/seletskiy/godiff
