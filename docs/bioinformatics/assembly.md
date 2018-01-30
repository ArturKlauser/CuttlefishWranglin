# Genome Assembly

## Tutorial
In this tutorial we will walk through assembling a smaller (6.8G bases) yeast genome using the [SPAdes Genome Assembler](http://bioinf.spbau.ru/spades).
> NOTE: This tutorial assumes you are running either Linux and OS X. Refer to the [SRA Toolkit Documentation](https://trace.ncbi.nlm.nih.gov/Traces/sra/sra.cgi?view=toolkit_doc) for Windows instruction.

1. Download the [NCBI SRA Toolkit](https://trace.ncbi.nlm.nih.gov/Traces/sra/sra.cgi?view=software) which allows for downloading the sequence data.
2. Follow the [instructions](https://trace.ncbi.nlm.nih.gov/Traces/sra/sra.cgi?view=toolkit_doc&f=std) for your operating system.
3. Run a test outlined in the instrucitons above to make sure its working as expected and you know how to run the commands. For example, Linux and OS X can run `./fastq-dump -X 5 -Z SRR390728` which just produce the following output.
  ```
  Read 5 spots for SRR390728
Written 5 spots for SRR390728
@SRR390728.1 1 length=72
CATTCTTCACGTAGTTCTCGAGCCTTGGTTTTCAGCGATGGAGAATGACTTTGACAAGCTGAGAGAAGNTNC
+SRR390728.1 1 length=72
;;;;;;;;;;;;;;;;;;;;;;;;;;;9;;665142;;;;;;;;;;;;;;;;;;;;;;;;;;;;;96&&&&(
@SRR390728.2 2 length=72
AAGTAGGTCTCGTCTGTGTTTTCTACGAGCTTGTGTTCCAGCTGACCCACTCCCTGGGTGGGGGGACTGGGT
+SRR390728.2 2 length=72
;;;;;;;;;;;;;;;;;4;;;;3;393.1+4&&5&&;;;;;;;;;;;;;;;;;;;;;<9;<;;;;;464262
@SRR390728.3 3 length=72
CCAGCCTGGCCAACAGAGTGTTACCCCGTTTTTACTTATTTATTATTATTATTTTGAGACAGAGCATTGGTC
+SRR390728.3 3 length=72
-;;;8;;;;;;;,*;;';-4,44;,:&,1,4'./&19;;;;;;669;;99;;;;;-;3;2;0;+;7442&2/
@SRR390728.4 4 length=72
ATAAAATCAGGGGTGTTGGAGATGGGATGCCTATTTCTGCACACCTTGGCCTCCCAAATTGCTGGGATTACA
+SRR390728.4 4 length=72
1;;;;;;,;;4;3;38;8%&,,;)*;1;;,)/%4+,;1;;);;;;;;;4;(;1;;;;24;;;;41-444//0
@SRR390728.5 5 length=72
TTAAGAAATTTTTGCTCAAACCATGCCCTAAAGGGTTCTGTAATAAATAGGGCTGGGAAAACTGGCAAGCCA
+SRR390728.5 5 length=72
;;;;;;;;;;;;;;;;;;;;;;;;;;;;;9445552;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;446662
  ```
4. Create a `data` directory for downloading data with the command `mkdir data && cd $_`.
5. Download the [Demo data](https://www.ncbi.nlm.nih.gov/sra/ERX1365588[accn]) with the command `../sratoolkit.2.8.2-1-mac64\ 2/bin/fastq-dump --gzip ERR1294016`. This assumes you are in the data directory and your fastq-dump is in the path designated.
> NOTE: This will take awhile! Its downloading 3.3G bytes
