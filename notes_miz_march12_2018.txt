# coding_challenge_final.vcf has 7000 variants, 33 of them multiallelic
# To plit these multiallelic lines into separate lines, I used the existing tool "vcf_parser"
# Installed VCF Parser from https://github.com/moonso/vcf_parser
# Ran vcf_parser from Command line:

vcf_parser coding_challenge_final.vcf --split > coding_challenge_vcf_parser_split.vcf

# Uploaded split vcf file to the Ensembl Variant Effect Predictor
# http://useast.ensembl.org/Tools/VEP
# Options:
# Transcript database to use: Ensembl transcripts
# Identifiers: Gene Symbol
# Frequency data: 1000 Genomes global minor allele frequency
# Rest: default options

# Downloaded annotated vcf file
# Note: An extensive table of the annotated variants can be donloaded directly from the website.

# Ran custom Perl script to extract desired information and output it in tab-separated table format.

vcf_extract_info.pl coding_challenge_vcf_parser_split_annotated.vcf > coding_challenge_table_output.txt

# Column headers from the output table
1	#CHR
2	POSITION
3	REF
4	ALT
5	TYPE
6	DEPTH
7	VAR_DEPTH
8	VAR_READ_PERC
9	AF
10	EFFECT
11	SCORE

#There were 41 distinct possible effects and corresponding impact scores found
EFFECT SCORE
3_prime_UTR_variant	MODIFIER
3_prime_UTR_variant&NMD_transcript_variant	MODIFIER
5_prime_UTR_variant	MODIFIER
5_prime_UTR_variant&NMD_transcript_variant	MODIFIER
downstream_gene_variant	MODIFIER
frameshift_variant	HIGH
inframe_deletion	MODERATE
inframe_insertion	MODERATE
intergenic_variant	MODIFIER
intron_variant	MODIFIER
intron_variant&NMD_transcript_variant	MODIFIER
intron_variant&non_coding_transcript_variant	MODIFIER
mature_miRNA_variant	MODIFIER
missense_variant	MODERATE
missense_variant&NMD_transcript_variant	MODERATE
missense_variant&splice_region_variant	MODERATE
non_coding_transcript_exon_variant	MODIFIER
regulatory_region_variant	MODIFIER
splice_acceptor_variant	HIGH
splice_acceptor_variant&intron_variant	HIGH
splice_acceptor_variant&intron_variant&non_coding_transcript_variant	HIGH
splice_acceptor_variant&non_coding_transcript_variant	HIGH
splice_donor_variant	HIGH
splice_donor_variant&intron_variant	HIGH
splice_region_variant&3_prime_UTR_variant	LOW
splice_region_variant&5_prime_UTR_variant	LOW
splice_region_variant&coding_sequence_variant&intron_variant	LOW
splice_region_variant&intron_variant	LOW
splice_region_variant&intron_variant&NMD_transcript_variant	LOW
splice_region_variant&intron_variant&non_coding_transcript_variant	LOW
splice_region_variant&non_coding_transcript_exon_variant	LOW
splice_region_variant&synonymous_variant	LOW
start_retained_variant&5_prime_UTR_variant	LOW
stop_gained&frameshift_variant	HIGH
stop_gained	HIGH
stop_gained&NMD_transcript_variant	HIGH
stop_lost	HIGH
stop_retained_variant&3_prime_UTR_variant	LOW
synonymous_variant	LOW
synonymous_variant&NMD_transcript_variant	LOW
upstream_gene_variant	MODIFIER

# Created GitHub account and uploaded files
https://github.com/mizav/test
