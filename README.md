Graph-theoretic analysis of morphological voice networks

Author: Matthew Zaslansky (University of California, San Diego, Department of Linguistics)

Version: 2.0.1 (Pre-Release Build)

Version date: 31 January 2025

####################

Introduction to the Pre-Release Build

This repository contains R code that implements graph-theoretic and information-theoretic analyses of the morphological voice networks of several languages. The core theoretical foundations of this analysis is based on the analyses carried out by Sims & Parker (2019) and Sims (2020), in which inflection class systems are conceptualized as networks with the distinct (micro-)classes as nodes connected by edges which represent the inter-class analogical potential of shared exponents. "Conceptualized thusly, the distribution of exponents across classes more generally Ð can be quantified in terms of network properties." (Sims & Parker 2019)

First and foremost, the R code in this release implements network visualizations and a range of standard graph-theoretic calculations over inflection class networks: degree, edge weight, clustering coefficient, connected components, shortest path length, betweenness centrality, modules, node role. Mostly the calculations are for individual networks, but the code implements some minimal comparison based on global clustering coefficient and mean shortest path length, comparing the individual networks to each other, and also to randomized versions of the same class systems (based on Monte Carlo simulations).

Additionally, the code implements probability and entropy calculations for individual paradigm cells, and mean values for the inflectional system as a whole. Conditional entropy is calculated pairwise over individual cells in the style of Ackerman et al. (2009, Parts and wholes: Implicative patterns in inflectional paradigms) and Ackerman and Malouf (2013, Morphological organization: The Low Conditional Entropy Conjecture). 

Finally, it calculates "entropy difference" -- the amount of average conditional entropy in a network minus the amount of average conditional entropy with one node (class) removed -- and graphs correlations between network properties and entropy difference, to facilitate evaluation of how network properties contribute to the 'complexity' of the inflection class system.

The six scripts in this release are designed to facilitate quantitative, cross-linguistic comparison of inflectional systems based on their systemic internal organization;

The main function calls are in main.R. When the working directory is the same as the directory containing the scripts, 

source("main.R")
main.fnc(all_files)

will run all major functions -- calculations and graphs -- for all files in language_plats/ . An unlimited number of language plats is accommodated.

network.fnc() calculates various graph-theoretic measures of each inflectional network, makes network and other graphs, and writes out summary files of network properties. It only calculates measures for each language individually.

comparison.fnc() graphs some limited comparisons across all plats -- e.g. plotting mean shortest path length against global clustering coefficient -- and adds Monte Carlo simulations of each language.

entropy.fnc() makes probability/entropy calculations: probability of exponents (unconditioned and conditioned on one other exponent), unconditioned entropy of a cell, entropy of a cell conditioned on one other cell (in the style of Ackerman et al. 2009 and Ackerman and Malouf 2013). It also calculates "entropy difference" -- the difference between the mean conditional entropy of paradigm cells in a full inflectional system and the mean conditional entropy of paradigm cells of the same system with one class removed. It iterates through all classes in the plat and outputs a summary file for each modified IC system.


2.0.1 CONTENT UPDATES 

KARAKALPAK

Added.

KAZAKH

Added.

####################

REFERENCES

Ackerman, Farrell, James P. Blevins, and Robert Malouf. 2009. Parts and wholes: Implicative patterns in inflectional paradigms. In Analogy in grammar: Form and acquisition, ed. by James P. Blevins and Juliette Blevins, 54-82. Oxford: Oxford University Press.

Ackerman, Farrell and Robert Malouf. 2013. Morphological organization: The Low Conditional Entropy Conjecture. Language 89(3): 429-464.

Sims, Andrea D., with contribution by Jeff Parker. 2019. Inflectional networks: Resources for graph-theoretic analysis of linguistic morphology, v. 1.0.1 [24 December 2019]. DOI: 10.5281/zenodo.3594436 

Sims, Andrea D. 2020. Inflectional networks: Graph-theoretic tools for inflectional typology. Proceedings of the Society for Computation in Linguistics 3: Article 10, 88-98. https://scholarworks.umass.edu/scil/vol3/iss1/10
