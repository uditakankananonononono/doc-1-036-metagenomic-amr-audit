# DOC-1-036 F0 RESULTS: documentation-only feasibility audit

Unit: DOC-1-036, source position 36, "Predicting Antimicrobial Resistance from Metagenomes".
Audit type: F0 metadata feasibility under the locked protocol (PROTOCOL_LOCKED.md, commit 29afe42da776b849736d535dbd04c70b4a2e567f). No sequences, antibiotic-susceptibility values, ARG abundance tables, model outputs or scoring opened. Zero scientific success credit. No clinical use. Prediction/audit only: no resistance engineering, sequence design, mutation ranking or treatment recommendation.

## Verdict

UNRESOLVED for the full source36 question on the fixed route set. Zero success credit.

- A CARD data readme, B RGI README, C ResFinder README: tools/databases, not datasets. M1-M3 UNKNOWN-by-construction, as pre-stated in the locked protocol. No CARD or ResFinder database content was downloaded.
- D EBI AMR portal developers page: standalone STOP at M2. The record explicitly states genotypes are "AMR genes and mutations from in silico methods" and that records are isolate/assembly-level, with the merged view joined on BioSample_ID, assembly_ID and antibiotic_ontology. Explicit statement, not absence; this matches the pre-stated FAIL rule. The phenotype view is measured antibiogram data (non-circular, pre-stated case c), but at isolate level it cannot supply the metagenomic input.
- E Serpa 2022 (Genome Medicine): UNRESOLVED. M1-M4 have documentary support for a single-site metagenome-to-cultured-isolate pairing design, with the pre-stated coverage limit written below. M5 is unmet: one site (UCSF), one group; BioProjects PRJNA450137 and PRJNA635133 come from one group and are not independent cohorts under the locked rule; one site is below the pre-stated minimum. Per-drug positive/negative denominators are not verifiable at metadata level because Table 1 was not opened: UNKNOWN. M6 reuse terms for sequences and phenotype data: UNKNOWN.
- F PMC8173267 (population-level faecal metagenomics, Cambodia/Kenya/UK): UNRESOLVED. The design is ecological at population level: pooled faecal metagenomes versus AST metadata of invasive Enterobacterales isolates from the same settings, collected from different individuals and partly different time windows. M5 multi-site support is partial (three sites under one documented common-protocol study); M6 is UNKNOWN (host-DNA fraction control not documented in the extracted methods; reuse terms for sequences, AST metadata and curated datasets UNKNOWN). The design is also narrower than the sample-level source36 question.

This is not a full fixed-set STOP: E and F are not affirmatively incompatible with an honest design. No narrower lead is promoted; isolate-genomic AMR prediction and population-level ecological prediction are partial leads that would each need a separately registered question.

## Chronology

- Locked protocol: PROTOCOL_LOCKED.md, commit 29afe42da776b849736d535dbd04c70b4a2e567f, GitHub-displayed server timestamp 2026-10-09T22:02:06Z. SHA256 a9a0cbb9d6839595aee788e30817fe21520b038d686f1f0d3902d20b2f6aa4d8, verified byte-identical at tag f0-protocol-lock via independent readback.
- Tag/release f0-protocol-lock: page-observed server datetime 2026-10-09T22:02:47Z. Per gate instruction, the later time 22:02:47Z is the chronology cutoff.
- First admission fetch: 2026-10-09T22:03:00Z (routes A-E), route F 2026-10-09T22:03:02Z. Both strictly after the 22:02:47Z cutoff.
- All six routes admitted; expected identifier markers matched on each route.

## Raw captures and hashes

Raw captures for E and F hold Results-section text that was left unread, per the locked extraction rule (same convention as unit 095). Extraction was limited to design, methods and data-availability text; article figure images and outcome-table cells were not opened.

Observed route URLs and capture SHA256 (bytes as fetched, UTF-8 markdown):

- A https://card.mcmaster.ca/readme/data : 7c81b4341bbc9492c7ef44f06baee08bbc2c9545400ac3d12d7b85f745e16fc1
- B https://github.com/arpcard/rgi : c9c2e83b1ca84c8a7f9c2abc5db704329c00ba280beee6efaa1508fa60f5d968
- C https://github.com/genomicepidemiology/resfinder/blob/master/README.md : 5b167c9242a07f16b1b2532bfd91289a7b0f1a553fdd6fd53c692c74e8ca6d5e
- D https://www.ebi.ac.uk/amr/developers/ : f16a7a38cd43a74299b21a1c4555107b5488e08575bc3bf843005a5b7f9c9c73
- E https://link.springer.com/article/10.1186/s13073-022-01072-4 : c430176cc35c5e839e6ab25971aeb53f8b0388d78ed2813d98bdde7fd1284f5b
- F https://pmc.ncbi.nlm.nih.gov/articles/PMC8173267/ : 38e808f5fafb5d79683ce3d6a3784cc49966f5fc222b54b5995ff69a1cb17e44
- Curated design extracts below: E extract SHA256 907738def72f5dd74caec060110540e68df03a0f7471d92226c87ff821571d73 ; F extract SHA256 8268d0b8c5f5a9322270737a76dd3d37c19f85b7419079bf244f045ead02e677
- Fetch-time records: first-fetch-utc.txt SHA256 223090b463087c6d0055b6e970f0174485351d49fab8e00a6972f4b596989f80 ; F-fetch-utc.txt SHA256 b8cc340d35629a0a5c44fb866aa34d43250c976123ef1c5081f7d3fe20a803c9

## Per-route gate matrix (M1-M6)

A CARD readme: M1 UNKNOWN-by-construction; M2 UNKNOWN-by-construction; M3 UNKNOWN-by-construction; M4 n/a (no label design proposed); M5 n/a; M6 UNKNOWN: commercial use or reproduction by any commercial organization prohibited without written McMaster permission (tool terms only, no redistribution rights established). Route text notes the data are appropriate for BLAST analysis of metagenomic data.

B RGI README: M1-M3 UNKNOWN-by-construction. Own wording: "Software to predict resistomes from protein or nucleotide data, including metagenomics data, based on homology and SNP models." License stated as "Other" plus the CARD restriction wording. M6 UNKNOWN. M4 note: RGI in-silico genotype-to-phenotype calls are pre-stated circular (case a); no such label design was run.

C ResFinder README: M1-M3 UNKNOWN-by-construction. Own wording: "ResFinder 4.0 for predictions of phenotypes from genotypes" and input scope "sequenced isolates of bacteria"; outputs include pheno_table.txt / pheno_table_species.txt (database-derived phenotype tables, pre-stated circular case a). Tool license Apache-2.0 licenses the software only, not sequence or phenotype data. M6 UNKNOWN.

D EBI AMR developers: M1 PASS-in-principle for phenotypes (antibiogram measurements, CLSI/EUCAST standards documented; isolate unit), M2 FAIL for any standalone design (explicit in-silico genotypes and isolate/assembly records), M3 FAIL for the metagenomic question (join keys BioSample_ID/assembly_ID/antibiotic_ontology are isolate/assembly-level), M4 non-circular for measured phenotypes, M5 not assessed (design stopped at M2), M6 UNKNOWN (reuse terms for parquet data not stated on the page). Schema field lists were opened; example values in the schema (e.g. SAMEA1028830, SMRU2695) are documentation illustrations, not observations. No parquet file was downloaded or queried; the count query shown on the page is a documentation example and was not executed.

E Serpa 2022: M1 PASS (reference standard "clinical AST results performed in the UCSF Clinical Microbiology Laboratory", CLSI MIC breakpoints; isolate-level measured phenotypes). M2 PASS (RNA and DNA metagenomic sequencing of respiratory samples). M3 SUPPORTED WITH LIMIT (metagenomic sample paired to culture-confirmed pathogens from the same patient with clinical AST; pre-stated coverage limit applies: cultured taxa are a minority and isolate phenotype is not the community phenotype; primary analysis 27 patients / 32 culture-confirmed pathogens). M4 PASS for this design (labels from the clinical laboratory; features from ARG-ANNOT/CARD homology annotation; different measurement processes). M5 UNMET (single site, single group; PRJNA450137 and PRJNA635133 not independent cohorts under the locked rule; below the pre-stated minimum of 3 cohorts/sites; per-drug denominators UNKNOWN at metadata level). M6 PARTIAL/UNKNOWN (Illumina platform and human-genome subtraction documented, dpM depth normalization documented, ARG-ANNOT "expanded version" and CARD used without pinned versions in the extracted text; article is CC BY 4.0 which does not license sequence or phenotype data; sequence reuse terms UNKNOWN).

F PMC8173267: M1 PASS at isolate unit (AST results collated from site microbiology laboratories, standard operating procedures per international guidelines). M2 PASS (shotgun metagenomic sequencing of faecal extracts, HiSeq 4000; 90 individual metagenomes plus 3 thirty-sample pools and 3 population pools = 96 metagenomes, a design count). M3 SUPPORTED WITH LIMIT at population unit only (pooled metagenome metrics modelled against AST of invasive isolates from the same setting; different individuals and partly different collection windows; ecological aggregation limit; isolate phenotypes are not the community phenotype). M4 PASS (labels measured by microbiology labs; features are CARD v3.0.3-mapped gene counts; different measurement processes). M5 PARTIAL (three sites: Kilifi Kenya, Siem Reap Cambodia, London UK, distinct populations under one documented common-protocol multi-site design; antibiotic contexts restricted to drugs with AST data in at least 2 of 3 settings; taxa within Enterobacterales; binomial tested/resistant denominators documented in the methods; single study group, so independence rests on the common-protocol clause). M6 UNKNOWN (CARD v3.0.3 and platform documented; host-DNA fraction control not documented in the extracted methods; ENA PRJEB34871 sequence terms, Mendeley dataset terms and AST metadata reuse terms UNKNOWN; article CC BY does not license the data).

FAIL vs UNKNOWN: the only affirmative incompatibility is D at M2/M3 (explicit in-silico and isolate/assembly wording). All other unmet gates are UNKNOWN or UNRESOLVED by the pre-stated rules, not FAIL.

## Fields and counts opened per route

- A: restriction wording, model-type wording, metagenomic-BLAST suitability note. No counts.
- B: tool claim wording, analysis-mode list, license wording. No counts.
- C: scope wording, output file names, version statement, license wording. No counts.
- D: schema field lists for the phenotype, genotype and merged parquet views; join keys; illustrative example values disclosed above. No dataset counts; the documentation example query was not run.
- E: Study design section (cohort design counts: 70 LRTI and 18 non-infectious subjects; primary analysis 27 patients and 32 culture-confirmed pathogens), methods subsections on extraction, sequencing, bioinformatics, AMR gene detection and the AST reference standard, and the data-availability section (BioProject identifiers, not followed). Results section, Table 1 contents, figures and supplementary files not opened.
- F: Methods sections 2.1-2.9 (settings, pooling, sequencing, processing, metric definitions, statistical design, ethics) and the Data sharing section (PRJEB34871, ResPipe GitLab URL, Mendeley DOI; none followed). Design count opened: 96 metagenomes. Results sections 3.1-3.6, figures and appendix not opened.

## Exposure ledger

Pre-lock discovery (unchanged from the locked protocol): recorded URLs https://card.mcmaster.ca/readme/data ; https://github.com/arpcard/rgi ; https://github.com/genomicepidemiology/resfinder/blob/master/README.md ; https://www.ebi.ac.uk/amr/developers/ ; https://docs.mgnify.org/src/docs/portal.html ; https://zenodo.org/records/16213507 ; https://link.springer.com/article/10.1186/s13073-022-01072-4 ; https://pmc.ncbi.nlm.nih.gov/articles/PMC8173267/ . Recorded queries: `"Metagenomic prediction" "01072" "data" "accession"` and `ResFinder documentation phenotype prediction license metagenomic`. Unrecorded discovery cannot be excluded. Search highlights incidentally showed performance-flavored phrases (">99.9% concordance", "robust dataset of 18,916"); exposure, not evidence, and no threshold, ranking or gate was chosen from them. MGnify is named in source36 but is not a fixed route and was not audited. E's PRJNA identifiers are recorded as identifiers only and were not followed.

Post-lock exposure: raw E and F captures contain unread Results-section text as stated. Route D schema illustrations disclosed above. No outcome values from E or F were read or used.

## Deviations

1. E methods extraction initially included figure/table captions (no images, no outcome-table cells) and wet-lab methods text for the targeted-enrichment sub-study. Neither was used as evidence; both were removed from the curated extract below. The raw capture retains them unaltered.
2. F extraction includes the full Methods block as published, which contains model-design detail; it contains no outcome values.

## Curated evidence extracts

Own-record wording relied on for label semantics, join keys and design statements. Results-section text excluded.

### E Serpa 2022: curated design and availability extract

### Study design

We studied 70 mechanically ventilated patients with LRTI and 18 with non-infectious respiratory illnesses (Fig. 1, Additional File 1: Table S1) who were admitted to the University of California San Francisco (UCSF) Medical Center between 07/2013 and 9/2018. Subjects with LRTI were identified by two-physician adjudication using the United States Centers for Disease Control/National Healthcare Safety Network (CDC/NHSN) surveillance case definition [13], a reference list of established respiratory pathogens [6], and retrospective electronic medical record review, blinded to mNGS results. Study inclusion criteria were age ≥ 18, need for mechanical ventilation, and lower respiratory specimen (tracheal aspirate (TA) or mini-bronchoalveolar lavage (mBAL)) collected within 72 h of intubation. Patients were excluded if they declined study participation, had unclear LRTI status, or did not have matched RNA and DNA mNGS data available from a respiratory specimen (Fig. 1).

Primary analyses were performed for 27 patients, secondary analyses for all subjects. The primary analysis focused on patients with bacterial LRTI due to culture-confirmed pathogens that had been clinically tested for susceptibility to antimicrobials (n = 27 patients, n = 32 pathogens) (Fig. 1, Table 1, Additional File 2: Table S2). Of these, 18 patients had respiratory samples sequenced for a prior mNGS study by our group [6]. For secondary analyses, 43 additional patients with clinically adjudicated LRTI and 18 patients with no evidence of LRTI were assessed. In total, the secondary outcome analysis of hospital exposure and AMR gene burden in the respiratory microbiome assessed 70 patients with LRTI and 18 patients with no evidence of LRTI. Assessment of Cas9 targeted Illumina and nanopore sequencing for detecting AMR genes included 10 patients from the primary analysis with culture-confirmed bacterial LRTI.


#### Nucleic acid extraction and Illumina metagenomic sequencing

RNA extraction from mBAL or TA and Illumina metagenomic sequencing were carried out as described previously [6, 14].

#### Pathogen detection bioinformatics

Detection of respiratory microbes leveraged the ID-Seq pipeline [14] that incorporates the STAR [15] aligner to subtract the human genome (NCBI GRC h38), quality filtering with PRICESeqfilter [16], and additional filtering to remove non-microbial sequences. The identities of the remaining microbial reads were determined by querying the NCBI nucleotide (NT) and non-redundant protein (NR) databases using GSNAP-L and RAPSEARCH2, respectively [14]. Microbial alignments detected by RNA-seq and DNA-seq were aggregated to the genus level and the sequencing reads comprising each genus were then evaluated for taxonomic assignment at the species level based on species relative abundance. A recently developed rules-based model (RBM) [6] was employed to differentiate putative pathogens from commensal microbiota.

The RBM leverages previous findings demonstrating that microbial communities in patients with LRTI are typically characterized by one or more dominant pathogens present in high abundance [6, 14]. More specifically, the RBM ranks microbial genera present in a sample by descending abundance (number of taxonomic alignments). The greatest difference between any two sequential taxa is then identified to capture genera present at disproportionately high abundance compared to the rest of the lung microbiota [6, 17].

All genera with an abundance greater than this largest gap threshold are then evaluated at the species level, by identifying the most abundant species within each genus. If the species is present within a previously curated reference index of established respiratory pathogens [6, 17] derived from landmark epidemiologic surveillance studies [18, 19, 20, 21, 22], it is selected as a putative pathogen by the RBM. A detailed description of the principles and clinical validation of the RBM has been previously published [6, 17].

#### Detection of AMR genes

AMR genes present in RNA-seq or DNA-seq data were identified using SRST2 coupled with an expanded version of the ARG-ANNOT database [23] (Additional File 3), and genes with ≥ 5% allele coverage were included in analyses. Because Streptococcus pneumoniae is a leading cause of bacterial LRTI [4], we also screened for point mutations in pbp genes associated with Streptococcus beta lactam resistance using the CARD resistance gene identifier tool and the ‘loose’ setting [24]. Average read depth across each allele, normalized by gene length and total reads (depth per million reads sequenced, dpM), was calculated for each sample.

#### Assessing performance of genotypic antimicrobial susceptibility prediction

As a reference standard, we used clinical AST results performed in the UCSF Clinical Microbiology Laboratory during each patient’s admission. To calculate sensitivity and specificity, which was done both by microbe and by drug (Table 1), we compared mNGS-based resistance predictions against phenotypic AST determined by the Clinical & Laboratory Standards Institute minimum inhibitory concentration breakpoints [25]. We studied samples from subjects with culture-confirmed bacterial pathogens for which AST was performed. One isolate that only underwent chromogenic beta lactamase screening was excluded. Two subjects (252, 297) with highly polymicrobial cultures of ≥ 4 organisms were also excluded due to the unclear clinical significance of the isolated microbes. This left a primary analysis cohort of 27 patients and 32 bacterial pathogens (Fig. 1).

We assessed susceptibility to the most common antibiotics used for complicated infections from bacterial pathogens identified in the cohort: S. aureus, S. pneumoniae, E. faecium, Enterobacteriaceae, P. aeruginosa, and S. maltophila. Initial AMR gene class assignment (beta lactam, aminoglycoside, macrolide/lincosamide/ streptogramin, glycopeptide, trimethoprim/ sulfamethoxazole) was made using ontology in ARG-ANNOT [23] and a more refined AMR phenotype assignment was made based on CARD [24] resistome ontological relationships. In addition to sensitivity and specificity, we assessed very major error (VME; predicted susceptible but phenotypically resistant) and major error (ME; predicted resistant but phenotypically susceptible) rates.

#### Clinically tested antimicrobials used in mNGS AMR prediction benchmarking

Resistance predictions were made for antibiotics routinely tested in the clinically microbiology laboratory for Staphylococcus aureus, Streptococcus pneumoniae, Enterococcus faecium, Pseudomonas aeruginosa, Stenotrophomonas maltophila, and Enterobacteriaceae. For S. aureus these included penicillin, methicillin, clindamycin or erythromycin, trimethoprim/ sulfamethoxazole (TMP/SMZ), and vancomycin; for S. pneumoniae: penicillin, ceftriaxone, and vancomycin; for E. faecium: ampicillin and vancomycin; for Enterobacteriaceae: ampicillin + sulbactam, cefazolin, ceftriaxone, gentamicin, piperacillin-tazobactam, TMP-SMX, ertapenem, and meropenem; for P. aeruginosa: ampicillin + sulbactam, ceftazidime, gentamicin, piperacillin-tazobactam, and meropenem; and for S. maltophila: ceftazidime and TMP/SMZ. For some isolates, clinical susceptibility testing for certain antimicrobials was not performed by the clinical laboratory, and thus was unavailable for our analysis.

#### Mitigation of background contaminants

To minimize inaccurate taxonomic assignments due to environmental contaminants, we processed negative water controls with each group of samples that underwent nucleic acid extraction, and included these, as well as positive control clinical samples, with each sequencing run. We directly subtracted alignments to those taxa in water control samples detected by both RNA-seq and DNA-seq analyses from the raw reads per million (rpm) values in all samples [6]. To account for selective amplification bias of contaminants in water controls resulting from PCR amplification of metagenomic libraries to a fixed standard concentration across all samples, prior to direct subtraction, we scaled taxa rpms in the water controls to the median percent microbial reads present across all samples as previously described [6]. To address environmental contaminants in AMR gene analyses, resistance alleles detected in water controls at a depth > 1 were excluded.


## Availability of data and materials

Raw microbial sequences are available via NCBI BioProject PRJNA450137 [36], https://www.ncbi.nlm.nih.gov/bioproject/?term = PRJNA450137, and BioProject PRJNA635133 [37], https://www.ncbi.nlm.nih.gov/bioproject/?term = PRJNA635133. FLASHit [26] and SURPI rt [28] have been deposited on Github and are available for download at: https://github.com/czbiohub/flash and https://github.com/chiulab/SURPI-plus-dist, respectively.

### F PMC8173267: curated methods and data-sharing extract

## 2. Methods

### 2.1. Samples and settings

Faecal material collected after 2014 at pre-admission clinics or on admission to hospital from three age-groups and settings was studied, namely: children 1–59 months in Kilifi, Kenya; newborns in Siem Reap, Cambodia; and adults ≥18 years in London, UK (appendix p2). Rectal swabs and faecal samples have both been used as approaches for intestinal metagenomics [12,13], and give comparable results [14].

For each study site, microbiology metadata for blood/cerebrospinal fluid samples (as most robustly representative of truly invasive infections) collected within 0–72 h of admission to hospital (i.e. community-associated) from 01/Jan/2010–31/May/2017 were collated. Each site has a microbiology laboratory participating in external quality assurance schemes and accreditation processes (appendix p2). Samples were processed using standard operating procedures in accordance with international guidelines (appendix p2). Collated metadata included bacterial species and antibiotic susceptibility test (AST) results, specimen type, and basic patient details to validate aggregate-level stratification by age. Infection metadata were collated for individuals < 90 days of age in Cambodia, ≤ 60 months of age in Kenya and ≥ 18 years of age in the UK (appendix pp2-3).

### 2.2. DNA extraction

DNA was extracted from each sample using the MoBio PowerSoil® DNA isolation kit (Qiagen, Hilden, Germany), as per the manufacturer's instructions with optimisation steps to achieve sufficient DNA yields for sequencing (ideally ≥300 ng DNA/34ul, with a view to obtaining ≥20Gbp (Giga base pairs) of data per sample; appendix pp4-8).

### 2.3. Sample pooling

DNA extracts were stored at −20 °C prior to pooling and sequencing. For each study setting, we created a “population pool”, which consisted of the pooling of equimolar concentrations of all extracts from that setting with ≥1 ng DNA/μl. To validate our pooling approach (see appendix pp11, 18-19), we also created one smaller pool for each setting, a “30-sample pool”, which consisted of equimolar concentrations of 30 randomly selected extracts with ≥300 ng DNA/34μl. An aliquot from each extract included in the 30-sample pools was also sequenced individually for the validation (i.e. sequenced extracts from 90 individuals in total). An aliquot from all extracts sequenced individually and included in the 30-sample pools was also included in the population pools.

### 2.4. Metagenomic sequencing

Sequencing of all faecal sample DNA extracts (pools and individual extracts) was performed using the HiSeq 4000 Illumina platform, generating 150 bp paired-end reads (i.e. 96 metagenomes [n = 90 individual metagenomes, n = 3 30-sample pools, n = 3 population pools]; appendix p9).

### 2.5. Sequence data processing

Taxonomic abundance of bacterial species and AMR genes at individual and pooled sample levels was determined using a published bioinformatics pipeline, ResPipe [15]. This pipeline incorporates established approaches to taxonomic profiling, namely Kraken2 [16] and Bracken [17], and an adapted approach to quantifying AMR gene markers present in a metagenome by mapping sequences against the Comprehensive Antibiotic Resistance Database [18,19] (CARD, v.3.0.3) (for method details, see appendix p9). All AMR genes identified in any of the samples were included in the analysis. Since ResPipe reports the number of sequences that mapped to each AMR, in order to remove reference gene length bias, the AMR gene profiles - i.e. the numbers of sequences mapping to each AMR gene - were corrected using the following formula: corrected gene count (CGC) = (specific read count x average read length) / (AMR gene length x specific lateral coverage) where (1) specific read count is the number of sequences mapping exclusively to the reference AMR gene; (2) specific lateral coverage is the proportion of the AMR gene covered by sequences mapping exclusively to the gene; (3) AMR gene length is the length of the gene the sequence is mapped to; and (4) average read length is average length of reads that mapped to the AMR gene.

The CARD database classifies each reference AMR gene by its association with phenotypic resistance. To be in CARD, an AMR gene must be described in a peer-reviewed scientific publication, have its DNA sequence available in GenBank, and include experimental evidence of elevated minimum inhibitory concentration (MIC) over controls. [19] We used these data to map and aggregate counts of AMR genes/variants associated with resistance to specific antibiotics. We ranked the AMR genes/variants into two categories, reflecting to some extent the public health risks posed [20]. The first category, AMRDEF, included only AMR determinants with the CARD “Confers_Resistance_to_Antibiotic” relationship ontology term, whereby the gene is known to confer or contribute to clinically relevant resistance to a specific antibiotic [19]. The second category, AMRALL, contained corrected counts of all AMR determinants with clear experimental evidence of increasing the MIC, including those associated with clinically relevant resistance (as for AMRDEF), but also those without the definitive “Confers_Resistance_to_Antibiotic” relationship ontology term. In this study we have used “antimicrobial resistance (AMR) gene” to define any relevant marker of resistance, including genes that confer resistance by mutation (but can have a susceptible wild type), and genes that confer resistance through presence/absence.

### 2.6. Taxonomy-Adjusted antimicrobial resistance (AMR) metrics

We developed AMR metrics and taxonomy metrics from pooled metagenomes (i.e. “population pools”) to predict the number of resistant isolates causing infection in each setting. Resistance metrics (RCGC) aim to summarise information about relative abundance of genes conferring resistance for a given antibiotic. These are given through the sum of corrected gene counts (CGCs) of AMR gene variants associated with resistance to a given antibiotic, j (RCGCj), divided by the total CGC of all AMR genes in the pool. We considered two possibilities. First, RCGC_DEF considered only AMR determinants known to definitively confer clinically relevant resistance (using AMRDEF, as defined above). Second, RCGC_ALL was calculated for AMR determinants with clear experimental evidence of increasing the MIC (using AMRALL). Taxonomic metrics (RTax) aim to represent relative taxonomic abundance, and were given through the estimated abundance of a clinically relevant bacterial grouping divided by the total estimated abundance of bacterial taxa in the pool. Three bacterial groupings were evaluated: (i) the entire Enterobacterales order (RTax_E); (ii) species in the Enterobacteriaceae family only (RTax_e); and (iii) the grouping of the four most common and clinically relevant bacterial genera/species within the Enterobacteriaceae family across study sites (namely Escherichia coli, Klebsiella pneumoniae, Salmonella spp., Enterobacter spp.; (RTax_e4)). Our prediction models included at most one taxonomic and one resistance metric, and evaluated six resistance and taxonomy metric combinations in total. We refer to these six combinations as taxonomy-adjusted AMR metrics.

### 2.7. Statistical analysis

For each of the six taxonomy-adjusted AMR metrics, we fitted a Bayesian generalized linear model to the infection data and applied Bayesian model comparison based on out-of-sample prediction accuracy. This allowed us to assess the potential of each metric to predict antibiotic resistance amongst clinical invasive Enterobacterales isolates and to determine the most predictive metric. Using cross-validation as a tool for model comparison penalizes models that are overfitting the data. We used de-duplicated counts of isolates (unique bacterial species per antibiogram and patient-ID) for the analyses. We let i denote the setting (Cambodia, Kenya or UK), and j the antibiotic being evaluated. We assumed that counts of resistant isolates follow a binomial distribution. Our model then predicts the count of resistance (ri,j) amongst tested Enterobacterales isolates (ni,j) using a probability of resistance (pi,j; see appendix pp9-11 for details of model equations and parameters).

| logit(pi,j)=αj+β1,jRCGC,i,j+β2,jRTax,i | (1) |
| --- | --- |

We included only those antibiotics that had existing antibiotic susceptibility test (AST) data in ≥2 of three settings; missing observations were excluded from the likelihood evaluation. Due to the limited number of infection isolates with AST results (especially in Cambodia), we chose standard weakly informative priors for the intercept (αj) and the effect parameters (β1,j, β2,j; appendix pp9-11). In addition, we restricted the effect of AMR gene abundance to be positive, reflecting our view that only a positive association of AMR genes and clinical resistance is biologically reasonable. Each model was fit using Stan software [21] (v2.19.1), taking 50,000 samples after a burn-in period of 5000 samples using four independent chains. We assessed chain convergence by inspecting chain traceplots and ensuring small values of the R-hat chain convergence diagnostic (R-hat<0.01) [22].

The best taxonomy-adjusted AMR metric was selected using Bayesian leave-one-out cross validation [23], which estimates the model's pointwise out of sample prediction accuracy. Importantly, as opposed to assessments of within sample prediction, leave-one out cross-validation estimates how well a model is expected to predict new, unseen data points, and it thus penalizes models that are overfitting. In addition to the six model versions with the different taxonomy-adjusted AMR metrics, we also included in the comparison one baseline model with resistance metrics (RCGC) but without taxonomy metrics (RTax), one with only taxonomy metrics (RTax), and a baseline (null) model with only intercepts (keeping only αj). This was to assess the value of considering only taxonomy or only AMR metrics (i.e. whichever RTax or RCGC metric performed best in the models considering combinations), against the value of combining these into a taxonomy-adjusted AMR metric for predicting clinical resistance. The within sample fit of the best model (chosen based on cross-validation) and of the null model, was assessed using logarithmic scoring of the posterior predictions against the observed counts of resistant isolates. This type of scoring assigns low scores to models with highly diffuse (uncertain) predictive distributions, and also to narrow but wrongly placed distributions, and is rooted in information theory and the definition of entropy [24]. For settings and antibiotics where zero samples were tested, we imputed the sample size by computing the rounded mean of the sample sizes of the other two settings. Model comparisons and all further data analyses were performed in R-3.6.1 statistical software [25].

### 2.8. Ethical approvals

Ethical approval for faecal/rectal samples was already in place (KEMRI/SERU/CGMR- C/023/3161, OXTREC 47-15 [26]; OxTREC ref 1047-13 [27]; and REC: 14/LO/2085 [28,29]). Samples were only collected from patients who provided informed consent or, in the case of children, whose parents/guardians provided consent on their behalf. This study was approved by the Oxford Tropical Research Ethics Committee (Reference: 5126-16), with additional local ethics clearance for inclusion of Cambodian and Kenyan samples, and a substantial amendment to 14/LO/2085 (NRES London-Camberwell St Giles) for UK samples.

### 2.9. Role of funding source

The funders and sponsor of the study had no role in study design, data collection, data analysis, data interpretation, or writing of the report; the views expressed are those of the authors and not necessarily those of the funders or the sponsor. All authors had full access to all the data in the study and had final responsibility for the decision to submit for publication.


## Data sharing

The raw sequence data reported in this study have been deposited in the European Nucleotide Archive under accession number PRJEB34871. The code to extract CARD data, including relationship ontology terms that were required to generate the final datasets, plus any required input files, are available from the ResPipe GitLab repository (https://gitlab.com/hsgweon/ResPipe). This includes all commands and parameters run for with TrimGalore, Kraken2, Bracken, BBPMAP and ResPipe (the bioinformatics pipeline). The curated analysis datasets (Corrected gene counts; AMR_DEF; AMR_ALL; dataset for Bayesian analysis) can be found at https://data.mendeley.com/datasets/sxn6sw4r57/1(Mendeley Data, V1, doi: 10.17632/sxn6sw4r57.1) along with the R code used to produce these and the code to run the Bayesian analysis.

## Closeout statement

F0 verdict: UNRESOLVED, documentation-only, zero success credit. Chronology verified: locked protocol and tag predate all admission fetches. No value access, no scoring, no figures, no supplementary files. Any narrower follow-up (isolate-genomic prediction, population-level ecological prediction, database benchmarking) requires a separately registered question and its own locked protocol.
