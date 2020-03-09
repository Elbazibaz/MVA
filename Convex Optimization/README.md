# Algorithms for speech recognition and language processing
## TP2 : PCFG and Parsing

---
> <u>**Files description**</u>
>
> * <code>pre_process.py</code> : removes the functionnal tag in the PoS to avoid sparsity issues. 
> * <code>split_sets.py</code> : creates train/dev/test files from the provided sequoia treebank. 
>   The last 10% of the original dataset is used to create the test set.
> 
>
>
> * <code>grammar.py</code> : creates the pcfg based on the formatted (sentences) train set. 
>    Keep track of the frequency of lhs->rhs rules
>    and also the (word, tag) frequency.
> * <code>oov.py</code> : Class to handle the OoV words. Also load the word embeddings in polyglot-fr. 
> * <code>parser.py</code> :  choose the most probable tree parse based on the PCYK algorithm. 
> * <code>main.py</code> : handles every
>
---

## Setting 
> Make sure you have the **sequoia-corpus+fct.mrg_strict** (treebank) in your current directory. Create a folder called **data** in your current working directory.
> simply run the shellscript that is binded to all python files.

## Evaluation
> We use the **EVALB** library to evaluate our parser performance. Make sure you have downloaded the EVALB file from EVALB library (latest version).
> Once the parsing is done, execute the following bash commands:
> * <code>cd EVALB</code>
> * <code>make</code>
> * <code>./evalb -p sample/sample.prm ../data/test_f ../evaluation_data.parser_output</code> 
