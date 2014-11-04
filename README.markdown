# vim-sexp mappings for regular people

I'm really liking my first impressions of [vim-sexp][].  It's like paredit
minus a couple of parts of paredit that are impossibly tricky to implement in
Vim.  I'm not too keen on some of the default mappings, though, and in
particular the mappings using the meta key are just an absolute deal breaker
for me and everyone else that uses Vim in a terminal.  So I made and published
my own, in an attempt to define a more accessible standard.

[vim-sexp]: https://github.com/guns/vim-sexp

## Installation

You know the drill.  Here's a copy and paste to install the works with
[pathogen.vim](https://github.com/tpope/vim-pathogen).

    cd ~/.vim/bundle
    git clone git://github.com/tpope/vim-sexp-mappings-for-regular-people.git
    git clone git://github.com/guns/vim-sexp.git
    git clone git://github.com/tpope/vim-repeat.git
    git clone git://github.com/tpope/vim-surround.git

## Provided mappings

These mappings supplement rather than replace the existing mappings (despite
vim-sexp's best efforts to thwart this), so if you have muscle memory, fear
not.

### Motion mappings

Vim-sexp uses meta mappings to move element-wise.  I've taken over the WORD
motions--`W`, `B`, `E`, `gE`--instead, operating under the theory that those
aren't nearly as useful in a language where so many punctuation marks are
identifier characters.  This might be a terrible idea.

### List manipulation mappings

More meta madness in the defaults here.  I've taken `>f` and `<f` to move a
form and `>e` and `<e` to move an element.

Slurpage and barfage are handled by `>)`, `<)`, `>(`, and `<(`, where the
angle bracket indicates the direction, and the parenthesis indicates which end
to operate on.

### Insertion mappings

Use `<I` and `>I` to insert at the beginning and ending of a form.

### Mappings inspired by surround.vim

Note that surround.vim out of the box works great with the sexp.vim motions
and text objects.  Use `ysaf)`, for example, to surround the current form with
parentheses.  To this, we add a few more mappings:

* `dsf`: splice (delete surroundings of form)
* `cse(`/`cse)`/`cseb`: surround element in parentheses
* `cse[`/`cse]`: surround element in brackets
* `cse{`/`cse}`: surround element in braces

## License

Copyright © Tim Pope.  Distributed under the same terms as Vim itself.
See `:help license`.
