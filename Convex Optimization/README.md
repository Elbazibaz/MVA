# Algorithms for speech recognition and language processing
## MVA - TP2 : PCFG and Parsing

---
> <u>**Files description**</u>
>
> * <code>pre_process.py</code> : removes the functionnal tag in the PoS to avoid sparsity issues. 
> * <code>split_sets.py</code> : creates train/dev/test files from the provided sequoia treebank. 
>   The last 10% of the original dataset is used to create the test set.
> 
>
>
> * <code>grammar.py</code> : contains the code related to the pcfg, which is built based on the formatted (sentences) train set. 
>    This class keeps track of the frequency of lhs->rhs rules and also the (word, tag) frequency.
>    The aforementionned quantities are used during the PCKY algorithm.
>    
> * <code>oov.py</code> : contains the code related to handle the OoV words. Also load the word embeddings in polyglot-fr. 
>                         Also contains the parser's core part, i.e. the heuristic strategies in <code>get_similarity_word</code>.
> * <code>parser.py</code> :  contains PCYK algorithm code. PCYK outputs the most probable tree parse.  
> * <code>main.py</code> : creates the relevant object to perform end-to-end parsing (train+predictions). 
>                          Writes the results in **evaluation_data.parser_output**.
>
---

## Setting 
> Make sure you have the **sequoia-corpus+fct.mrg_strict** (treebank) in your current directory. Create a folder called **data** in your current working directory.
> Then, simply run the shellscript that is binded to all python files. There is not particular options implemented. 

## Evaluation
> We use the **EVALB** library to evaluate our parser performance. Make sure you have downloaded the EVALB file from EVALB library (latest version) and that the folder is in your current working directory.
> Once the parsing is done, execute the following bash commands:
> * <code>cd EVALB</code>
> * <code>make</code>
> * <code>./evalb -p sample/sample.prm ../data/test_f ../evaluation_data.parser_output</code> 
>
> It will output detailed parsing results such as the TAG accuracy, the number of sentence successfully parsed ...
