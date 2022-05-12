# TCR-specific_epitope_querying_2022

1 - Before `TCRdist3`
-------------------

Input : 

* Public TCR database
* your TCRs

Concatenate your TCRs with the DB's TCRs. It's easier if your TCRs are at the top of the table. If the table is too big for `TCRdist3`, you can split it into several parts.

You have to remove all `NA`, empty values, etc (things that `TCRdist3` does not recognize).



2 - `TCRdist3` install and use
----------------------------

Install `TCRdist3` in a conda env

```
conda create -n tcrdist3 python=3.8.5
conda activate tcrdist3
pip3 install parasail		(1.2.4)
pip install tcrdist3
pip install notebook ipython
```

Put the modified "ruggiero" files in the folder below :
/path/to/tcrdist3/lib/python3.8/site-packages/tcrsampler/db/

If you need it, you have the alphabeta_gammadelta_db.tsv file :
/path/to/tcrdist3/lib/python3.8/site-packages/tcrdist/db/

```
conda activate tcrdist3
jupyter notebook
```

You can open the link of the Jupyter Notebook in a web browser.



3 - After `TCRdist3`
------------------

Results from `TCRdist3` are summarized in `results/FinalTable/Final_table.csv`.

The higher the affinity of two TCRs for the same epitope is, the lower the distance
calculated by `TCRdist3` will be. We thus chose to keep TCRs from the databases for which
the distance is less than or equal to 10.
