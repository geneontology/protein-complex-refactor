Notes and working files for Ontology Group refactoring of PC

 * [pc-leaves-no-ldef.tsv](pc-leaves-no-ldef.tsv) : LEAF nodes with NO equiv axiom
 * [pc-leaves-with-ldef.tsv](pc-leaves-with-ldef.tsv) : LEAF nodes WITH equiv axiom
 * [pc-non-leaves.tsv](pc-non-leaves.tsv) : NON-LEAF NODES (col 3 is list of differentiae)

A non-leaf node must have a class-level representation to retain the same inferences

Leaf nodes are *candidates* for removal from GO. Of these, if they
have a ldef (which usually involves function for non-leaves) then this
is a good candidate for retention.
