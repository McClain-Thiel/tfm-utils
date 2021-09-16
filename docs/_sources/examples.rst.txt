Examples
==========


`JASPAR <http://jaspar.genereg.net>`_ is a very highly-touted transcription factor motif database from which motif count matrices can be downloaded for a large variety of organisms and transcription factors. There exist numerous other motif databases as well (TRANSFAC, CIS-BP, MEME, HOMER, WORMBASE, etc), most of which use a relatively similar format for their motifs. Typically, a motif file consists of four rows or columns with each position in a given row or column corresponding to a base within the motif. Sometimes there is an comment line started with ``>``. The row or column order is always ``A, C, G, T``. In this example, the motif consists of four rows corresponding to the 16 positions of the motif with counts for each base at each position.

>>> from tfm_utils import tfmp
>>> m = tfmp.create_matrix("MA0045.pfm")
>>> tfmp.score2pval(m, 8.7737)
9.992625564336777e-06
>>> tfmp.pval2score(m, 0.00001)
8.773708000000001

This could also be done by creating a string for the matrix by concatenating the rows (or columns) and using the

>>> from tfm_utils import tfmp
>>> m = tfmp.create_matrix("MA0045.pfm")
>>> tfmp.score2pval(m, 8.7737)
9.992625564336777e-06
>>> tfmp.pval2score(m, 0.00001)
8.773708000000001

This could also be done by creating a string for the matrix by concatenating the rows (or columns) and using the

>>> from pytfmpval import tfmp
>>> m = tfmp.create_matrix("MA0045.pfm")
>>> tfmp.score2pval(m, 8.7737)
9.992625564336777e-06
>>> tfmp.pval2score(m, 0.00001)
8.773708000000001

This could also be done by creating a string for the matrix by concatenating the rows (or columns) and using the ``read_matrix()`` function. This method is usually easier, as it allows the user to parse the motif file as necessary to ensure a proper input. It's also more fitting for high-throughput use.

>>> from tfm_utils import tfmp
>>> mat = (" 3  7  9  3 11 11 11  3  4  3  8  8  9  9 11  2"
...        " 5  0  1  6  0  0  0  3  1  4  5  1  0  5  0  7"
...	   " 4  3  1  4  3  2  2  2  8  6  1  4  2  0  3  0"
...	   " 2  4  3  1  0  1  1  6  1  1  0  1  3  0  0  5"
...	  )
>>> m = tfmp.read_matrix(mat)
>>> tfmp.pval2score(m, 0.00001)
8.773708000000001
>>> tfmp.score2pval(m, 8.7737)
9.992625564336777e-06

>>> from tfm_utils import tfmp
>>> mat = (" 3  7  9  3 11 11 11  3  4  3  8  8  9  9 11  2"
...        " 5  0  1  6  0  0  0  3  1  4  5  1  0  5  0  7"
...	   " 4  3  1  4  3  2  2  2  8  6  1  4  2  0  3  0"
...	   " 2  4  3  1  0  1  1  6  1  1  0  1  3  0  0  5"
...	  )
>>> m = tfmp.read_matrix(mat)
>>> tfmp.pval2score(m, 0.00001)
8.773708000000001
>>> tfmp.score2pval(m, 8.7737)
9.992625564336777e-06

>>> from pytfmpval import tfmp
>>> mat = (" 3  7  9  3 11 11 11  3  4  3  8  8  9  9 11  2"
...        " 5  0  1  6  0  0  0  3  1  4  5  1  0  5  0  7"
...	   " 4  3  1  4  3  2  2  2  8  6  1  4  2  0  3  0"
...	   " 2  4  3  1  0  1  1  6  1  1  0  1  3  0  0  5"
...	  )
>>> m = tfmp.read_matrix(mat)
>>> tfmp.pval2score(m, 0.00001)
8.773708000000001
>>> tfmp.score2pval(m, 8.7737)
9.992625564336777e-06
