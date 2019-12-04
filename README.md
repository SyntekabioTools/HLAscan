# HLAscan
## HLAscan Introduction
1. Overview<br>
HLAscan is an alignment-based program that determines haplotypes taking read distribution into account. The software performs alignment of reads to HLA sequences from the international ImMunoGeneTics project/human leukocyte antigen (IMGT/HLA) database.<br>
The distribution of aligned reads was used to calculate a score function to determine correctly phased alleles by progressively removing false-positive alleles. HLAscan can be reliably applied for determination of HLA type across the whole-genome, exome, and target sequences.

2. License terms<br>
HLAscan software is freely available for academic purposes and a license is required for commercial download and installation. Please contact service@syntekabio.com for questions regarding the license.

3. Reference<br>
[Ka, S., Lee, S., Hong, J., Cho, Y., ... & Jung, J. (2017). HLAscan: genotyping of the HLA region using next-generation sequencing data. BMC bioinformatics, 18(1), 258.](https://bmcbioinformatics.biomedcentral.com/track/pdf/10.1186/s12859-017-1671-3)

 



## HLAscan_v2
1. Updates<br>
(1) HLAscan v2 is compatible with human reference (hg19(v37) and v38).<br>
(2) Bam file and Fastq files can get to as an HLAscan v2 input.<br>
(3) Increase the ease of use.<br>
(4) Optimizations<br>
HLAscan v2 uses Suffix Array (SA) method instead of BWA-mem for alignment with IMGT/HLA Database.<br>
    - Time efficiency : about 10 times faster than previous version (ex: under a minute for HLA-typing (<100dp)) 
    - Space efficiency :  < 20MB disk (no create intermediate files)

2. Contents<br>
(1) DB<br>
HLA-ALL.IMGT : IMGT/HLA database<br>
(2) Tool<br>
hla_scan_r_v2.1.4

3. Usage<br>
    (1) Download the DB & Tool<br>
    (2) Read Manual<br>
    ```bash
    ./hla_scan
    ```
    (3) Execute the tool<br>
    - Bam Input
        ```bash
        ./hla_scan –b [Bam file] –v [37/38] –d [DB] –g [Gene Symbol] –t [# of threads]
        ```
    - Fastq Input
        ```bash
        ./hla_scan –l [fastq file] (-r [fastq file2]) –v [37/38] –d [DB] –g [Gene Symbol] –t [# of threads]
        ```

4. Commands<br>
    (1) HLA typing (input : bam file)<br>
    ```bash
    ./hla_scan -b [bam] -d [IMGT/HLA DB] -v [version(37 or 38)]
    ```
    (2) HLA typing (input : fastq files)<br>
    ```bash
    ./hla_scan -l [fastq] (-r [fastq2]) -d [IMGT/HLA DB]
    ```

5. Options<br>
    (1) Gene List -g [string], default=HLA-A<br>
    >HLA-A, HLA-B, HLA-C, HLA-E, HLA-F, HLA-G, MICA, MICB,<br>
    HLA-DMA, HLA-DMB, HLA-DOA, HLA-DOB, HLA-DPA1, HLA-DPB1, HLA-DQA1,<br>
    HLA-DQB1, HLA-DRA, HLA-DRB1, HLA-DRB5, TAP1, TAP2<br>

    (2) Score Cutoff -s [int], default=50<br>
    (3) Constant using ScoreFunc -c [int], default=30<br>
    (4) # of threads -t [int], default=32

## Download
You can download programs from the links underneath or from the [release page](https://github.com/SyntekabioTools/HLAscan/releases)
- HLAscan v2.1.4<br>
[HLAscan v2.1.4](https://github.com/SyntekabioTools/HLAscan/releases/download/v2.1.4/hla_scan_r_v2.1.4)

- HLAscan v2.1.3 (An error in specific case is fixed.)<br>
[HLAscan v2.1.3](https://github.com/SyntekabioTools/HLAscan/releases/download/v2.1.3/hla_scan_r_v2.1.3)

- HLAscan v2.1.2 (An error in specific case is fixed.)<br>
[HLAscan v2.1.2](https://github.com/SyntekabioTools/HLAscan/releases/download/v2.1.2/hla_scan_r_v2.1.2)

- HLAscan v2.1.1<br>
[HLAscan v2.1.1](https://github.com/SyntekabioTools/HLAscan/releases/download/v2.1.1/hla_scan_r_v2.1.1)

- HLAscan v2.1.0<br>
[HLAscan v2.1](https://github.com/SyntekabioTools/HLAscan/releases/download/v2.1.0/hla_scan_r_v2.1)

- HLAscan v2.0<br>
[HLAscan v2.0 Manual.pdf](https://github.com/SyntekabioTools/HLAscan/releases/download/v2.0.0/HLAscan.v2.0.Manual.pdf) [Files: [HLAscan v2.0](https://github.com/SyntekabioTools/HLAscan/releases/download/v2.0.0/hla_scan_r_v2.0)]

- HLAscan v1.0<br>
[HLAscan v1.0 Manual.pdf](https://github.com/SyntekabioTools/HLAscan/releases/download/v1.0.0/HLAscan.v1.0.Manual.pdf)  [Files: [HLAscan v1.0 Files.zip](https://github.com/SyntekabioTools/HLAscan/releases/download/v1.0.0/HLAscan.v1.0.Files.zip)]

## Dataset
You can download the dataset from [here](https://github.com/SyntekabioTools/HLAscan/releases/download/v2.0.0/dataset.zip).
