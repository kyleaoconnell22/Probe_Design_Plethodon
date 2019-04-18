0_annotate_trans.py

This script will take a text file of transcript annotations and append these to the names of your transcript fasta. Examples are in the script. If you transcriptome is already annotated, you can skip this step.

1_IDexon_single_genelist.py (and also multi gene list.py)

This script will filter the gene phred file to chose only one (or all in the case of the multi script) exon from the coding sequence and output a new list of exons and their location in the reference genome.

2.1_splice_ref_exons.py

This script will take the output from script 1, as well as a reference genome, in this case the Ambystoma reference, and create a new pseudoreference that is splice to only exonic sequence. This allows us to approximately find exon boundaries in our transcripts so we do not target probes across introns. The output is a new spliced reference. 

3_blast_Transcripts_to_Ref.py

Blast the transcripts against the new spliced reference to find exon sequence in the annotated transcripts.

4_filter_blastout_splice_CDS.py

Filter the blast results down to the best hit per transcript. Then, splice the transcripts to select one exon per transcript, and only select transcripts that are annotated in the transcript and in the reference genome so that you can identify these genes downstream. Then it will splice your transcriptome into the target exons, and randomly select the desired number of exons if you have more than you need according to a user defined number. 

6.1_splice_immune_transcripts.py

Pull out transcripts associated with immune function. This could be modified to find transcripts with any desired function, such as certain vision genes etc. 


