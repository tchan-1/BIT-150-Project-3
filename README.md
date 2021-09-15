# Project 3

### Introduction

#### Tool Overview
ResFinder is a tool that is used to identify bacteria that have gained genes/chromosomal mutation which confer antimicrobial resistance, through the analysis of the bacteria's DNA sequence.

ResFinder works in four main steps. The first step is choosing whether to look for point mutation and/or acquired antimicrobial resistance genes. The second step is selecting a species. The third step is to choose a sequencing technology/type of reads being submitted. The last step is to upload the genetic data for the given species, whether it be genomic, proteomic, or short sequence reads.  

#### How It Works

ResFinder works by comparing the genome from an input file and aligning it against multiple antimicrobial resistance genes. It computes a %Identity score which is the percentage of aligment between the input and the resistance genes from ResFinder. The threshold for this can be adjusted by the user. ResFinder also provides a Query/HSP length, and the minimum length the tool searches for can also be set by the user.

#### Uses, Requirements, and Types of Input
ResFinder is useful in determining whether a certain strain from a certain bacterial species has any antimicrobial resistance genes. If it does have those genes, the tool can tell the user which genes the species has, and how many it has. In a broader application, the tool is useful in comparing the difference in resistance genes between two strains of the same species. 

In order to run ResFinder, the only thing a user needs is a file containing reads for their species of interest. Multiple types of file input are supported by ResFinder. Accepted file inputs include: Assembled Genome/Contigs, 454 - single end reads, 454 - paired end reads, Illumina - single end reads, Illumina - paired end reads, Ion Torrent, SOLiD - single end reads, SOLiD - paired end reads, and SOLiD - mate pair reads. For Genome/Contig files, ResFinder requires the file format to be FASTA. Similarly Illumina and Torrent files must also be FASTA, but they can also be FASTQ. 454 (aka Roche GS) files can in FASTA, FASTQ, fna, or sff formats. SOLiD files can formatted as either qual or cfasta.


### Methods

In order to determine what antimicrobial resistance genes were located in the a-virulent strain: Ec_55989, I first checked off "Acquired antimicrobial resistance genes". I left the Antimicrobial configuration to its default setting, which selects all antimicrobials. I also left "threshold for %ID", and "minimum length" as their defualt values, which were 90% and 60% respectively. I then selected "Escherichia coli" as the species, and "Assembled Genome/Contig" as the type of reads. Following that, I isolated the file "Ec_55989.contigs.fa" from my computer, and uploaded.

To see which antimicrobial resistance genes were in the virulent strain: Ec_TY248, I began by again checking off the box for "Acquired antimicrobial resistance genes". I then left the default settings/values for Antimicrobial configuation, "threshold for %ID", and "minumum length". The defualt settings/values are the same as stated above. I selected "Escherichia coli" as the sepcies and "Assembled Genome/Contig" as the type of reads. I isolated the file "Ec_TY2482.contigs.fa" and uploaded it.

### Results

#### Results for Ec_TY2482 strain (virulent strain):
![](https://i.imgur.com/B0BAEKY.png)


#### Results for Ec_55989 strain (a-virulent strain):
![](https://i.imgur.com/k8pbwLW.png)

From the output, I found that the Ec_TY2482 strain was resistant to quite a few antimicrobials which include: cefepime, ampicilin, cefotaxime, sulfamethoxazole, trimethoprim, tetracylcine, and ceftazidime. For the Ec_55989 strain, I found that it was only resistant to tetracycline, which is quite a stark difference in comparison to the Ec_TY2482 strain. 

#### Altered Tool Option Results:

Default (right) vs Altered %ID (left), for Ec_TY2482
![](https://i.imgur.com/NhYXVfY.png)

Default (right) vs Altered %ID (left), for Ec_55989
![](https://i.imgur.com/NwIJdSj.png)

I altered the threshold for %ID, and raised it from 90% to 100%. For both strains, this did not affect the overall significant results. Both strains still had the same number of resistance genes before and after the change in threshold. However, the sub tables listing out specific genes for each antimicrobial did change for each strain. The tool uses a color code in order to denote how well part of the input genome matches to any microbial resistance genes. The darker green indicates a perfect match for a resistance gene, while the lighter green indicates a non-perfect match. After changing the threshold, and genes that did not match 100% were removed from the subtables, which meant every light green colored entry was taked out.


### Discussion
Results are discussed - including the overall patterns, as well as specific genes identified. The results are compared to the existing literature. Similarities in the findings from specific papers are highlighted. An explanation is provided for why the selected program option did or did not change the output 
#### Findings
From the results I gathered, I found there to be several main differences between strains Ec_TY2482 and Ec_55989. The first notable differenceis that the virulent strain (Ec_TY2482) is resistant to 14 more antimicrobials than the a-virulent strain. The list of genes identified within Ec_TY2482 is: aph(3'')-Ib: (streptomycin), aph(6)-Id: (streptomycin), sul2: (sulfamethoxazole), dfrA7: (trimethoprim), blaCTX-M-15:(amoxicillin,ampicillin,aztreonam,cefepime,cefotaxime,ceftazidime,ceftriaxone,piperacillin,ticarcillin) , blaTEM-1B:(amoxicillin,ampicillin,cephalothin,piperacillin,ticarcillin), mdf(A): (unknown macrolide,unknown aminoglycoside,unknown tetracycline,unknown fluoroquinolone,unknown phenicol,unknown rifamycin), (mdf(A)Y08743): (unknown macrolide,unknown aminoglycoside,unknown tetracycline,unknown fluoroquinolone,unknown phenicol,unknown rifamycin), and tet(A):(doxycycline,tetracycline	). The gene identified in Ec_55989 is tet(B) (doxycycline,tetracycline,minocycline	)
The information within the parenthesis, beside each gene indicates which antimicrobials the gene confers resistance to. One interesting comparison between the two strains, is that both are resistant to tetracyclin, but each has a different gene for that purpose.



#### Comparison to paper
The main antimicrobials that I found Ec_TY2482 to be resistant to, are nearly the same ones that researchers found for the same strain, in the paper titled "Comprehensive Characterization of Escherichia coli O104:H4 Isolated from Patients in the Netherlands". 

#### Explanation for change in program option
The increase in threshold for %ID in regards to how well the input sequnce matched the resistance gene did  affect the results overall. When the threshold was set to 90% (its default), the tool found that Ec_TY2482 had 2 more resistance genes than when the threshold was set to 100%. This is due to the fact that the genes had a slightly imperfect match with the input sequence, and therefore were counted out in the more stringent option.

