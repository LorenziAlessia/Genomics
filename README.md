# Molecular diagnosis of rare genetic disorders in ten individuals

## Overview
Hereditary diseases are caused by mutations in one or more genes in the DNA sequence, which lead to a gain or a loss of the full functionality of the transcript; variants pass from parents to children by autosomal and/or sex chromosomes and could be dominant (even de novo) or recessive.

In order to search and identify those mutations, a useful approach is represented by the <b>parent-child trios exome sequencing</b>.

In this final assessment project for the <i>"Genomics"</i> course at University of Milan, a colleague of mine and I worked with exome sequencing of chromosome 16 of ten trios of individuals (mother, father, child), where parents are known to be healthy and the child could be affected by a rare mendelian disease.

The aim of the study is to correctly <b>diagnose any possible genetic disease that could affect a child</b> out of a set of ten cases.


## Matherials and Methods

### Data
The professor provided:
* Reads data about ten different trios in form of `.fq` files. The cases we had to analyze were: 1651, 1665, 1679, 1700, 1762, 1768, 1793, 1806, 1816 and 1841.
* `universe.fasta` file, along with its index files, which is our *hg19 reference genome* for chr16
* `exons16Padded_sorted.bed` file, which specifies the target regions.

### Methods
1. Read the trios in `.fq` format
2. Preprocessing
    1. Alignment
    2. Indexing
    3. Coverage
    4. Variant calling
3. Variant prioritization
4. Disease description

This is more specifically explained in the "Report.pdf" file.

## Results
| **CASE** | **POSITION** | **REF** | **ALT** | **CONSEQUENCE** | **GENE** | **DISEASE** |
|------|----------|-----|-----|-------------|------|---------|
| 1651 | 16:56913454-56913458 | CCAT | CAT | Frameshift variant, splice region variant | SLC12A3 | **Familial hypokalemia - hypomagnesemia** |
| 1665 | 16:89811472-89811472 | C | T | Stop gained | FANCA | **Fanconi anemia complementation group A** |
| 1679 | 16:3900810-3900810 | G | A | Stop gained | CREBBP | **Rubinstein-Taybi syndrome due to CREBBP mutations** |
| 1700 | 16:89806419-89806422 | AGA | A | Frameshift variant | FANCA | **Fanconi anemia complementation group A** |
| 1762 | 16:2143899-2143901 | GC | C | Frameshift variant | PKD1 | **Autosomal dominant polycystic kidney disease** |
| 1768 | - | - | - | - | - | **HEALTHY** |
| 1793 | 16:56553661-56553666 | CCCGT | CCGT | Frameshift variant | BBS2 | **Bardet-Biedl Syndrome** |
| 1806 | - | - | - | - | - | **HEALTHY** |
| 1816 | 16:3801726-3801726 | C | A | Splice donor variant | CREBBP | **Rubinstein-Taybi syndrome due to CREBBP mutations** |
| 1841 | 16:2142954-2142954 | C | A | Splice donor variant | PKD1 | **Autosomal dominant polycistic kidney disease** |

## Analysis
Only two out of the total ten cases were diagnosed as “healthy”, while the other eight were diagnosed with a mutation associated to a rare mendelian disease.

The mutation in **case 1651** is related to familial hypokalemia-hypomagnesemia as primary phenotype, characterized by hypokalemic metabolic alkalosis with hypomagnesemia and hypocalciuria. It's the most common renal tubular disorder among Caucasians. 
Clinical features include transient periods of muscle weakness and tetany, abdominal pains, and chondrocalcinosis.

For **cases 1679** and **1816** the mutations are instead related to Rubinstein-Taybi syndrome, that causes congenital anomalies, such as microcephaly, characteristic facial dismorphisms, wide thumbs and toes, and intellectual disability with behavioral problems.

**Cases 1665** and **1700** are found to be affected by Fanconi Anemia, that causes an increased risk of cancer, bone marrow failure, physical defects and organ malformations.

The primary phenotype related to the mutations of **cases 1762** and **1841** is Autosomal dominant polycystic kidney disease. It is 
characterized by the development of renal cysts and various extra renal manifestations, such as intracranial aneurysms and dolichoectasias, abdominal wall hernias, mitral valve prolapse, and aortic root dilatation and aneurysms.

**Case 1793**'s primary phenotype related to the mutation is Bardet-Biedl Syndrome, mainly characterized by obesity, retinitis pigmentosa, polydactyly, hypogonadism and, in some cases, kidney failure.

Finally, instead, for **case 1768** and **case 1806**, no variants with a high impact were found to be associated with any rare disease. Therefore, we looked for variants with a moderate impact: missense variants with moderate impact were found on the CREBBP gene (location: 16:3820629-3820629, REF: G, ALT: T): hence, a possible cause for Rubinstein-Taybi syndrome. However, only PolyPhen labelled the variant as “possibly damaging”; other pathogenicity predictors like SIFT classified it as “tolerated” and the allele frequency according to gnomAD is not very low (>10-4). 
Thus, our final diagnoses for these cases were *healthy*.
