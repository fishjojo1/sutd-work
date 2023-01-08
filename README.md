# sutd-work
Some work done with professors of sutd in 2022


## Auxilary functions 

I *highly* recommend to write your own auxilary functions to work with files, as it will be much easier to write your own scripts than use our pre-existing ones and attempt to understand our bad code practices.

What the functions will be useful for however, will be understanding the syntax of how to run py2cfg and graph2vec


under graph2vec 

1. file_move.py moves files from submissions to the files folder (basically, ignore this)

2. make_cfg.py recursively creates cfgs of python scripts in /files into a nicely formatted json file.

3. param_run.py runs graph2vec on the various parameters and saves into graph2vec/py2cfg2vecV1.1/graph2vec-master/features(might be able to reuse this lol)

4. comment_remove.py (you can reuse this, but I wrote it quite roughly so there might be some room for catching some edge cases? not too sure) it removes comments before using py2cfg as they r represented in the graphs which will skew your results


## Analysis of graph2vec parameter efficiencys

This is the main part of the work that we did.

under anal.ipyb and anal2.ipyb, you'll find analysis of the various graph2vec parameters that we tried.

Most of the analysis were done on sample codes that calculated the fibonacci sequences with differing methodologies :)

### Key takeaways:

epoch: You need an epoch count of >100 at least before getting diminishing returns. We observe that this value increases as the code complexity increases

dimensions: Dimensions needed are quite subjective to the complexity of the code. Greater the complexity, greater the dimensions is the general case.

wl_iterations: we're not very confident on our results for this, just take a look at the graphs and you'll see why haha. got to experiment more

learning_rates: for what we can see so far, this one requires the most hypertuning. VERY subjective to the codebase

We also observe that graph2vec has no gpu support(due to the libraries it uses). If you want to dynamically bruteforce your way through a hypertune parameter set for a very complex codebase with ALOT of submissions, we highly recommend you try to modify it for gpu support. Else you can kinda hack your way through by taking a small but varied subset of the available codes.


