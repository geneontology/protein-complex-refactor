As you are aware, the term “protein complex” and progeny sits in the Cellular Component aspect of the GO. This branch of the ontology is designed to provide terms to describe where a gene product resides when performing it’s function. It contains organelles, which makes sense because gene products end up in different parts of the cell to do their thing. 
However, terms such as the protein complex children almost live outside of this use, as they are often used to describe the collective membership of  gene products in an object.  A specific  cellular location is usually not even used in the definition.
We appear to be cloning species specific complexes into the GO ontology.

When is a complex  species agnostic?
David H and others have proposed a simple test: can the GO complex term be logically defined by other GO terms? If it cannot be; if it can only be described by enumerating its components, then it should not belong in the GO, it’s non species agnostic.

Examples:

ribosome: GO:0005840 (long text definition, but doesn’t not list protein components)
Logical def:
 Isa ribonucleoproteiin complex GO:0030529
 Capable of: peptide bond formation  (not in GO: might want to add, or a function term)
 Capable of: translation elongation GO:0006414  (note: smaller ribosome subunit would be capable of: translation initiation and pre-initiation complex formation)
 There may be for that can be added here, I”m just quickly citing a couple off of my head.
If a mitochondrial ribosome, can also add: part-of mitochondrion

eukaryotic translation initiation factor 2 complex  GO:0005850 (text def notes a heterotrimeric complex; no specific proteins named)
Logical def:
 Isa protein complex
 Capable of:formation of translation initiation ternary complex GO:0001677
 Capable of: GTP binding  GO:0005525 (part of GO:0001677)
 Capable of: methionyl-initiator tRNA binding (term not present, would add, part of GO:0001677).

Neither of these make use of enumeration of their actual protein component names

Protein kinase complex: GO:1902911
Logical def:
Isa protein complex
Capable-of : protein kinase activity GO:0004672

Arp2/3 protein complex GO:0005885
A stable protein complex that contains two actin-related proteins, Arp2 and Arp3, and five novel proteins (ARPC1-5), and functions in the nucleation of branched actin filaments.
Logical def:
Isa  protein complex
Maybe “: capable-of Arp2/3 complex-mediated actin nucleation GO:0034314 (but this term seems to have been made for the complex??); Perhaps make an actin nucleation complex (generic) instead of Arp2/3 protein complex?, then capable of actin nucleation GO:0045010 

The main problem that we encounter is that too often, the logical def cannot be made specific enough such that two or more complexes might be defined only using the same terms:

Bam protein complex GO:1990063
Protein complex which is involved in assembly and insertion of beta-barrel proteins into the outer membrane. In E. coli it is composed of BamABCDE, of the outer membrane protein BamA, and four lipoproteins BamB, BamC, BamD and BamE. BamA interacts directly with BamB and the BamCDE sub complex.
Proposed logical def: 
Isa protein complex
Capable of:  protein insertion into membrane GO:0051205 I have a feeling that there may be other things that might do this and are protein complexes?
In this case, we might be able to use something that PRO uses: only-in-taxon?


On the use of complex terms to annotate a complex:
 In PRO: all complexes in PRO are partly logically defined as at least an ISA GO protein complex or deeper if a suitable term exists. The full logical definition includes has-component statements that point to specific protein ids (PRO proteoforms). Since it is already logically defined with the GO term, there is no point in annotate the entity  using the GO protein complex terms.

Although Intact does not use logical definitions (they aren’t an ontology), it nonetheless by creation of the complex id makes an assumed ISA protein complex. There is no further need to then annotate as being a complex. 

Both resources use multiple types of evidence and literature to support the existence of an entity; just like a UniProt protein object. Individual gene products are not annotated to “protein” using a GO term. 

Currently we have about  XNUMBERHERE complex terms in GO that cannot be logically defined using other GO terms, and are only defined by enumeration of protein names. Should these live in GO, or should they become IntACT/PRO complexes and thus become annotation objects, no different than any other gene product? They could have CC GO annotations (do they reside in the cytoplasm, nucleus, etc.), and any other specific function/process terms described by whatever paper is used for the annotations. 


How would  one annotate that a protein is a member of a complex (contributes-to)?
  Could use cc to protein complex with contributes-to, and then put a specific complex id (intact or PRO) in column 16?


-- 
Harold J Drabkin, Ph.D.
Senior Scientific Curator
Mouse Genome Informatics
The Jackson Laboratory
600 Main Street
Bar Harbor, ME 04609
voice:207-288-6650
fax: 207-288-6830
Email: harold.drabkin@jax.org
The information in this email, including attachments, may be confidential and is intended solely for the addressee(s). If you believe you received this email by mistake, please notify the sender by return email as soon as possible.
