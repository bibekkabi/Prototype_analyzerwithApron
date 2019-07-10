# Prototype_analyzerwithApron
A prototype analyzer, written in OCaml connected to APRON Abstract Domain Library 

The prime purpose of this analyzer is to infer inductive invariant for numerical programs.
The analyzer was originally developed by Antoine Miné which implemented the constraint programming algorithm of [1] 
using the boxes and octagons abstract domains of the Apron [2] library.  
Later, the prototype analyzer was modified to use the **zonotopic abstract domain Taylor1+** [3] and polyhedra abstract domain New Polka of Apron. 

The new elements included in the analyzer are: 

1. Now, the analyzer can handle multiple sub-parts after every split operation (see [1] for more information about the algorithm). 

2. A cheaper coverage (see [1] for more information about the algorithm) metric has been implemented which no longer relies on volume computation
   of abstract elements.
   
The steps to install and use the analyzer can be found in the document `00README.txt`. 
The modified version of the analyzer has been tested for different abstract domains namely boxes, octagons, polyhedra and zonotopes.

The analyzer relies on Apron library for the numerical abstract domains. 
For installing Apron, please follow the steps provided in the document `Pointers_apron.pdf`. 

The analyzer uses Taylor1+ implementation of Apron for the zonotope abstract domain. 
In order to extend the analyzer with zonotope abstract domain few new operations were implemented in Taylor1+. 
The details about them can be found in: https://github.com/bibekkabi/taylor1plus


# References

[1] Miné, A., Breck, J., & Reps, T. (2016, April). An algorithm inspired by constraint solvers to infer inductive invariants in numeric programs. In European Symposium on Programming (pp. 560-588). Springer, Berlin, Heidelberg.

[2] Jeannet, B., & Miné, A. (2009, June). Apron: A library of numerical abstract domains for static analysis. In International Conference on Computer Aided Verification (pp. 661-667). Springer, Berlin, Heidelberg.

[3] Ghorbal, K., Goubault, E., & Putot, S. (2009, June). The zonotope abstract domain taylor1+. In International Conference on Computer Aided Verification (pp. 627-633). Springer, Berlin, Heidelberg.
