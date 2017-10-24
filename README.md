## Purpose: 
Identify and annotate differnetially methylated regions between cellin es that have wild type EZh2 and the cell ines that have hyperactive EZH2

## Hypothesis: 
There is a correlation between EZH2 hypermutants and aberrant DNA methylation in GCB DLBCL cell lines (this is not the best written hypothesis. try to bring out the idea that EZH2 hypermutations -> more than normal H3K27me3 marks -> influence activities of DNA replciation and repair (AICDA), DNA methylation

## Cell Lines that we have now:
#Normal EZH2 : CRO.AP2 FARAGE HY OCI.LY.19 SU.DHL.5 SU.DHL.8
#Hyperactive EZH2 : DB(Y641N) KARPAS.422(Y641N) RL(Y641N) SU.DHL.6(Y641N) SU.DHL.4(Y641S) WSU.DLCL2(Y641F)

## Road map
# Create MethyGenoSet
Data needed: 
chromosome location
Exprs = data matrix of beta values 
Methylated 
Unmethylated
Detection =  p value of each beta value 
# Identify differentially methylated sites:
Sliding window smoothing to reduce measurement base using smoothMethydata (Windowsize (default) = 250bp)
Conduct Differential Methylation test using detectDMRslidewin (T- test and wilcox test)
Identify differentially methylated sites with Pvalue < 0.01 https://www.spandidos-publications.com/ol/14/3/2887 ) ->Rethink this part!!!!
# Identify differentially methylated regions
Using identifySigDMR\
Output = GRanges object indicating identified DMRs
sigDMRinfo
sigDatainfo -> Present to Greg!!
# Annotate DMRs
To understand genes/gene elements that are overlapping with the identified DMRs
Use annotate DMR info
TxDb (UCSChg19)
# Visualise - chromosome location based heatmap
Using heatmapByChromosome
