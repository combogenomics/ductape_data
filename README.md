ductape_data
============

This repository is intended to make the analysis of DuctApe on the test cases fully reproducible.
All the necessary input data are provided, as well as a detailed script to run each command used in the analysis.

Requirements
------------

* DuctApe v0.16.2 or later

* OrthoMCL

* InParanoid/MultiParanoid

Howto
-----

Choose the test set from the directories provided.

Once inside a directory, just type from the command line:

    ./runDuctApe

To perform the ortholog prediction benchmark (please note that the BLOSUM80 matrix has been used):

* The DuctApe orthologs are calculated as part of the runDuctApe script (file pangenome_category.tsv)

* InParanoid/MultiParanoid:
	
	* Compute the pairwise comparisons with the parapy script (orthologs folder)

	* Run MultiParanoid

	* Run the mp2tsv script (orthologs folder) to obtain the pangenome_category.tsv

* OrthoMCL:

	* Follow the OrthoMCL tutorial and obtain the groups.txt file; keep the compliantFasta directory

	* Run the omcl2tsv script (orthologs folder) to obtain the pangenome_category.tsv

The pangenome_category.tsv files can be easily compared using standard command line tools; for instance:

	cat pangenome_category.tsv | grep -c core

Will output the number of core genome orthologous groups that are present.

Comparison with published data
------------------------------

The acinetobacter and zmobilis folders contain data already published; the publications are the following:

* acinetobacter: Peleg, Anton Y., et al. "The success of acinetobacter species; genetic, metabolic and virulence attributes." PloS one 7.10 (2012): e46984.

* zmobilis: Bochner, Barry, et al. "Phenotype microarray profiling of Zymomonas mobilis ZM4." Applied biochemistry and biotechnology 161.1-8 (2010): 116-123.

Acknowledgements
----------------

* Dr. Bosi for the parapy script
* Dr. Bochner and Dr. Ziman for the Z. mobilis PM data
* Prof. Peleg and Dr. Dijkshoorn for the Acinetobacter PM data

