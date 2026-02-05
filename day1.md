#what i learnt today

testing to sync   

# MARKDOWN DAY ONE GUIDE
  
## Commands
+ help
+ touch
+ sl
+ cp
+ mk
+ sbatch
+ pwd
+ module avail
+ ssh -X : ssh -X sunam230@caucluster.rz.uni-kiel.de
+ $WORK
+ cd
+ micromamba env list

`logging into sunam account for the cluster and the micromamba environment that is appropriate is crucial.`

  # DAY 2 GUIDE
  ## 1. Quality control of raw reads
  run `fastqc` on several files named `*.fastq.gz`, which are compressed (zipped) sequencing reads files. 
  > `fastqc file.fastq.gz` : run `fastq` on `file.fastq.gz`  
  > `-o` : output folder  
   
   fastp allows you to process and filter the reads.
> `-i R1.fastq.gz` : input forward reads  
> `-I R2.fastq.gz` : input reverse reads  
> `-o output_folder/R1.fastq.gz` : output processed forward reads  
> `-O output_folder/R2.fastq.gz` : output processed reverse reads  
> `-t 6` : how many bases to trim from the tail of the forward reads  
> `-q 20` : Phred score threshold for filtering bases  
> `-h sample1.html` : name of the HTML-format report file  
> `-R "Sample 1"` : title for the output report file  
## 2. Assembly

Once the reads are filtered and cleaned by `fastp`, you can perform genome assemblies using `megahit`
> `-1` : input forward reads  
> `-2` : input reverse reads  
> `-o` : output directory  

To visualize the assembled contigs in `Bandage`, you need to convert the plain-text sequence file (`fasta`) into a fasta-like graph (`fastg`). To create a graph.
open `final.contigs.fastg` in `Bandage`. Once it is loaded (which might take a moment), click on `Draw graph` to visualize the contigs in the assembly.![alt text](image.png)

# DAY 3 GUIDE
 ![ ](image-1.png)
 
 # DAY 4
 ![alt text](image-2.png)
 ![alt text](image-3.png)
 ![alt text](image-4.png)
 ![alt text](image-5.png)
 ![alt text](image-6.png)
 ![alt text](image-8.png)
 ![alt text](image-7.png)
 ![alt text](image-9.png)
 ![alt text](image-10.png)
 ![alt text](image-11.png)
 ![alt text](image-12.png)
 ![alt text](image-13.png)
 ![alt text](image-14.png)
 ![alt text](image-15.png)
 ![alt text](image-16.png)
 ![alt text](image-17.png)
 ![alt text](image-18.png)
 ![alt text](image-19.png)
 ![alt text](image-20.png) core genome
 ![alt text](image-21.png) bin accessory
 ![alt text](image-22.png) singletons
![alt text](image-23.png) amino acid sequence for gene cluster
#DAY 7
![alt text](image-24.png)
![alt text](image-25.png)
![alt text](image-26.png)
![alt text](image-27.png)   


##DAY 9
How many free viruses are in the BGR_140717 sample?
[sunam230@caucluster1 BGR_140717_modified_summary]$ grep ">" BGR_140717_modified_virus.fna -c
846
[sunam230@caucluster1 proviruses_summary]$ grep ">" -c proviruses_virus.fna file.txt
proviruses_virus.fna:11
How many Caudoviricetes viruses are in all samples together? (Use the filtered version)
[sunam230@caucluster1 02_CHECK_V]$ grep "Caudoviricetes" BGR*/MVP_02_BGR_*_Filtered_Relaxed_Merged_Genomad_CheckV_Virus_Proviruses_Quality_Summary.tsv  -c
BGR_130305/MVP_02_BGR_130305_Filtered_Relaxed_Merged_Genomad_CheckV_Virus_Proviruses_Quality_Summary.tsv:614
BGR_130527/MVP_02_BGR_130527_Filtered_Relaxed_Merged_Genomad_CheckV_Virus_Proviruses_Quality_Summary.tsv:684
BGR_130708/MVP_02_BGR_130708_Filtered_Relaxed_Merged_Genomad_CheckV_Virus_Proviruses_Quality_Summary.tsv:850
BGR_130829/MVP_02_BGR_130829_Filtered_Relaxed_Merged_Genomad_CheckV_Virus_Proviruses_Quality_Summary.tsv:954
BGR_130925/MVP_02_BGR_130925_Filtered_Relaxed_Merged_Genomad_CheckV_Virus_Proviruses_Quality_Summary.tsv:849
BGR_131021/MVP_02_BGR_131021_Filtered_Relaxed_Merged_Genomad_CheckV_Virus_Proviruses_Quality_Summary.tsv:1079
BGR_131118/MVP_02_BGR_131118_Filtered_Relaxed_Merged_Genomad_CheckV_Virus_Proviruses_Quality_Summary.tsv:609
BGR_140106/MVP_02_BGR_140106_Filtered_Relaxed_Merged_Genomad_CheckV_Virus_Proviruses_Quality_Summary.tsv:368
BGR_140121/MVP_02_BGR_140121_Filtered_Relaxed_Merged_Genomad_CheckV_Virus_Proviruses_Quality_Summary.tsv:575
BGR_140221/MVP_02_BGR_140221_Filtered_Relaxed_Merged_Genomad_CheckV_Virus_Proviruses_Quality_Summary.tsv:717
BGR_140320/MVP_02_BGR_140320_Filtered_Relaxed_Merged_Genomad_CheckV_Virus_Proviruses_Quality_Summary.tsv:468
BGR_140423/MVP_02_BGR_140423_Filtered_Relaxed_Merged_Genomad_CheckV_Virus_Proviruses_Quality_Summary.tsv:358
BGR_140605/MVP_02_BGR_140605_Filtered_Relaxed_Merged_Genomad_CheckV_Virus_Proviruses_Quality_Summary.tsv:527
BGR_140717/MVP_02_BGR_140717_Filtered_Relaxed_Merged_Genomad_CheckV_Virus_Proviruses_Quality_Summary.tsv:559
BGR_140821/MVP_02_BGR_140821_Filtered_Relaxed_Merged_Genomad_CheckV_Virus_Proviruses_Quality_Summary.tsv:337
BGR_140919/MVP_02_BGR_140919_Filtered_Relaxed_Merged_Genomad_CheckV_Virus_Proviruses_Quality_Summary.tsv:476
BGR_141022/MVP_02_BGR_141022_Filtered_Relaxed_Merged_Genomad_CheckV_Virus_Proviruses_Quality_Summary.tsv:401
BGR_150108/MVP_02_BGR_150108_Filtered_Relaxed_Merged_Genomad_CheckV_Virus_Proviruses_Quality_Summary.tsv:339
How many Unclassified viruses are in all samples together? (Use the filtered version)
 grep "Unclassified" BGR*/MVP_02_BGR_*_Filtered_Relaxed_Merged_Genomad_CheckV_Virus_Proviruses_Quality_Summary.tsv  -c
BGR_130305/MVP_02_BGR_130305_Filtered_Relaxed_Merged_Genomad_CheckV_Virus_Proviruses_Quality_Summary.tsv:10
BGR_130527/MVP_02_BGR_130527_Filtered_Relaxed_Merged_Genomad_CheckV_Virus_Proviruses_Quality_Summary.tsv:9
BGR_130708/MVP_02_BGR_130708_Filtered_Relaxed_Merged_Genomad_CheckV_Virus_Proviruses_Quality_Summary.tsv:10
BGR_130829/MVP_02_BGR_130829_Filtered_Relaxed_Merged_Genomad_CheckV_Virus_Proviruses_Quality_Summary.tsv:14
BGR_130925/MVP_02_BGR_130925_Filtered_Relaxed_Merged_Genomad_CheckV_Virus_Proviruses_Quality_Summary.tsv:11
BGR_131021/MVP_02_BGR_131021_Filtered_Relaxed_Merged_Genomad_CheckV_Virus_Proviruses_Quality_Summary.tsv:14
BGR_131118/MVP_02_BGR_131118_Filtered_Relaxed_Merged_Genomad_CheckV_Virus_Proviruses_Quality_Summary.tsv:7
BGR_140106/MVP_02_BGR_140106_Filtered_Relaxed_Merged_Genomad_CheckV_Virus_Proviruses_Quality_Summary.tsv:4
BGR_140121/MVP_02_BGR_140121_Filtered_Relaxed_Merged_Genomad_CheckV_Virus_Proviruses_Quality_Summary.tsv:4
BGR_140221/MVP_02_BGR_140221_Filtered_Relaxed_Merged_Genomad_CheckV_Virus_Proviruses_Quality_Summary.tsv:8
BGR_140320/MVP_02_BGR_140320_Filtered_Relaxed_Merged_Genomad_CheckV_Virus_Proviruses_Quality_Summary.tsv:4
BGR_140423/MVP_02_BGR_140423_Filtered_Relaxed_Merged_Genomad_CheckV_Virus_Proviruses_Quality_Summary.tsv:4
BGR_140605/MVP_02_BGR_140605_Filtered_Relaxed_Merged_Genomad_CheckV_Virus_Proviruses_Quality_Summary.tsv:7
BGR_140717/MVP_02_BGR_140717_Filtered_Relaxed_Merged_Genomad_CheckV_Virus_Proviruses_Quality_Summary.tsv:9
BGR_140821/MVP_02_BGR_140821_Filtered_Relaxed_Merged_Genomad_CheckV_Virus_Proviruses_Quality_Summary.tsv:4
BGR_140919/MVP_02_BGR_140919_Filtered_Relaxed_Merged_Genomad_CheckV_Virus_Proviruses_Quality_Summary.tsv:8
BGR_141022/MVP_02_BGR_141022_Filtered_Relaxed_Merged_Genomad_CheckV_Virus_Proviruses_Quality_Summary.tsv:8
BGR_150108/MVP_02_BGR_150108_Filtered_Relaxed_Merged_Genomad_CheckV_Virus_Proviruses_Quality_Summary.tsv:10
What other taxonomies are there across all files? Below, paste a table with (at least) taxonomy, Genome type and Host type.
 grep -v "Caudoviricetes" 02_CHECK_V/BGR_*/MVP_02_BGR_*_Filtered_Relaxed_Merged_Genomad_CheckV_Virus_Proviruses_Quality_Summary.tsv |grep -v "Unclassified" |grep -v "Sample"
02_CHECK_V/BGR_130305/MVP_02_BGR_130305_Filtered_Relaxed_Merged_Genomad_CheckV_Virus_Proviruses_Quality_Summary.tsv:BGR_130305	BGR_130305_NODE_2265_length_4061_cov_5.941338	4061	No	3	1	0	Low-quality	Genome-fragment	2.89	AAI-based (medium-confidence)	1.0		11	0.9643	04.4395	Viruses;Varidnaviria;Bamfordvirae;Nucleocytoviricota;Megaviricetes;Imitervirales;Mimiviridae	dsDNA	Eukaryote
02_CHECK_V/BGR_130527/MVP_02_BGR_130527_Filtered_Relaxed_Merged_Genomad_CheckV_Virus_Proviruses_Quality_Summary.tsv:BGR_130527	BGR_130527_NODE_3972_length_2853_cov_3.214796	2853	No	3	1	0	Low-quality	Genome-fragment	4.0	HMM-based (lower-bound)	1.0		11	0.8411	0	3.4351	Viruses;Varidnaviria;Bamfordvirae;Nucleocytoviricota;Megaviricetes;Algavirales;Phycodnaviridae	dsDNA	Eukaryote
02_CHECK_V/BGR_130708/MVP_02_BGR_130708_Filtered_Relaxed_Merged_Genomad_CheckV_Virus_Proviruses_Quality_Summary.tsv:BGR_130708	BGR_130708_NODE_5125_length_2609_cov_6.036805	2609	No	3	1	0	Low-quality	Genome-fragment	3.65	HMM-based (lower-bound)	1.0		11	0.7483	0	3.4351	Viruses;Varidnaviria;Bamfordvirae;Nucleocytoviricota;Megaviricetes;Algavirales;Phycodnaviridae	dsDNA	Eukaryote
02_CHECK_V/BGR_131021/MVP_02_BGR_131021_Filtered_Relaxed_Merged_Genomad_CheckV_Virus_Proviruses_Quality_Summary.tsv:BGR_131021	BGR_131021_NODE_3917_length_3744_cov_3.725400	3744	No	4	1	0	Low-quality	Genome-fragment	1.08	AAI-based (medium-confidence)	1.0		11	0.9654	12.6771	Viruses	Unknown	Unknown
02_CHECK_V/BGR_131021/MVP_02_BGR_131021_Filtered_Relaxed_Merged_Genomad_CheckV_Virus_Proviruses_Quality_Summary.tsv:BGR_131021	BGR_131021_k141_151878_length_2551_cov_25.4033	2551	No	5	1	0	Low-quality	Genome-fragment	6.07	HMM-based (lower-bound)	1.0		11	0.9284	0	1.7183	Viruses;Varidnaviria;Bamfordvirae;Preplasmiviricota;Tectiliviricetes;Autolykiviridae	dsDNA	Prokaryote
02_CHECK_V/BGR_131021/MVP_02_BGR_131021_Filtered_Relaxed_Merged_Genomad_CheckV_Virus_Proviruses_Quality_Summary.tsv:BGR_131021	BGR_131021_NODE_12517_length_1678_cov_37.389402	1678	No	3	1	0	Low-quality	Genome-fragment	16.44	HMM-based (lower-bound)	1.0		11	0.9323	1	1.7183	Viruses;Riboviria;Pararnavirae;Artverviricota;Revtraviricetes;Ortervirales;Retroviridae	ssRNA-RT	Eukaryote
02_CHECK_V/BGR_140221/MVP_02_BGR_140221_Filtered_Relaxed_Merged_Genomad_CheckV_Virus_Proviruses_Quality_Summary.tsv:BGR_140221	BGR_140221_NODE_2074_length_4089_cov_7.783837_1_1_3696	3696	Yes	4	1	0	Low-quality	Genome-fragment	3.02	AAI-based (medium-confidence)	1.0	1-3696	11	0.9072	0	1.7183	Viruses;Varidnaviria;Bamfordvirae;Nucleocytoviricota;Megaviricetes;Algavirales;Phycodnaviridae	dsDNA	Eukaryote
02_CHECK_V/BGR_140605/MVP_02_BGR_140605_Filtered_Relaxed_Merged_Genomad_CheckV_Virus_Proviruses_Quality_Summary.tsv:BGR_140605	BGR_140605_NODE_5969_length_1911_cov_2.155172	1911	No	5	3	0	Low-quality	Genome-fragment	39.82	AAI-based (medium-confidence)	1.0		11	0.97	14.5511	Viruses;Monodnaviria;Sangervirae;Phixviricota;Malgrandaviricetes;Petitvirales;Microviridae	ssDNA	Prokaryote
02_CHECK_V/BGR_140919/MVP_02_BGR_140919_Filtered_Relaxed_Merged_Genomad_CheckV_Virus_Proviruses_Quality_Summary.tsv:BGR_140919	BGR_140919_NODE_1812_length_5087_cov_5.712838	5087	No	10	1	1	Low-quality	Genome-fragment	0.41	HMM-based (lower-bound)	1.0		11	0.9463	0	4.0154	Viruses	Unknown	Unknown
02_CHECK_V/BGR_140919/MVP_02_BGR_140919_Filtered_Relaxed_Merged_Genomad_CheckV_Virus_Proviruses_Quality_Summary.tsv:BGR_140919	BGR_140919_k141_2996_length_1161_cov_5.0000	1161	No	2	1	0	Low-quality	Genome-fragment	17.74	HMM-based (lower-bound)	1.0		11	0.959	1	1.5528	Viruses;Monodnaviria;Sangervirae;Phixviricota;Malgrandaviricetes;Petitvirales;Microviridae	ssDNA	Prokaryote
[sunam230@caucluster1 viromics]$ d
