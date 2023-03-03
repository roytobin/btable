
## BTable Testbench

A simple stimulus pattern generator, with checking, to test a scheme
implementation of a table data structure of key/value pairs implemented
using a binary tree.

> Exercise 3.26 SICP[^1] 1st & 2nd Ed
> To search a table as implemented above, one needs to scan through the list of
> records.  This is basically the unordered list representation of section 2.3.3.  For
> large tables, it may be more efficient to structure the table in a different manner.
> Describe a table implementation where the (key, value) records are organized
> using a binary tree, assuming that keys can be ordered in some way (e.g., nu-
> merically or alphabetically).  (Compare exercise 2.66 of chapter 2.)

### How to generate the self-checking stimulus

At the shell prompt ```./bttest >stim```

### Restrictions and Caveats
Peruse the generated stimulus to see what, if any, changes need to be made
to the exported procedures of the implementation under test (IUT) to align
with what the stimulus uses.  Small shim procedures may be required.

The IUT must return #f upon an unsuccessful lookup.  FYI, SICP 1st
Edition returned nil.

### Methodology
Randomize the object to be inserted into the table, the key to use
(string or number, see UsingInt in the the bttest script), and the
insertion order.  Insert these (key,value) pairs into two distinct tables.
Finally, check in random order against a reference model that all table
entries retain the correct value previously inserted.  Augment with many
additional unsuccessful lookups sprinkled throughout.

### Verification
The testbench was verified on Linux using these scheme implementations
1. s9 Scheme 9 from Empty Space by Nils M Holm, 2018-12-05
2. mit-scheme  Release 10.1.11 || Microcode 15.3 || Runtime 15.7
3. racket v7.9 [bc]

### See Also
* http://community.schemewiki.org/?sicp-ex-3.26
* [archived 24 Feb 2023](https://web.archive.org/web/20230224014615/http://community.schemewiki.org/?sicp-ex-3.26)

[^1]: *Structure and Interpretation of Computer Programs* by Harold Abelson et al. 1985, 1996
