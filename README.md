# 4-EMT-correlation-function-in-a-4d-CFT by Mirko Serino

This is a collection of the files I developed in order to perform and test the explicit calculation of the 4-point function
of the stress energy tensor in the free conformal field theory of a scala field in 4 spacetime dimensions.

Calculations of the 2 and 3 point functions are detailed as well, in order to provide a framework in which the reader can 
familiarize with the tools employes and with the ideas underpinning the calculations and their tests, if she/he is not yet 
familiar with them.

Some of the calculations can be quite time consuming and that the numerical checks of the Ward identities for 
the 4 point function requires your computer to have least 25 GB of memory at its disposal in order not to crush.

Mathematica (version 10.1 or higher).

PLEASE NOTE: 

1) "functional_derivatives.nb" MUST be run once in order to be able to run the rest of the calculation, 
particularly "correlators_calculation.nb", which in turn MUST be run in order to generate the correlation functions which are 
checked by "Ward_identities.nb".

2) The packages PackageX and CollierLink must be loaded on the machine where the notebooks are run. 

Here follows a concise description of the scope and purpose of each notebook: 

- The noteook "tensor_bases/tensor_bases_generation.nb" GENERATES the 4 files "tensmom#rank##". 
  As the name suggests, the tensors in each of these files 
  span a complete basis of tensors which are rank ## products of the metric tensor and # independent momenta. They are 
  needed to check the Ward identities for the 3 and 4 point correlation functions.
    
- "functional_derivatives.nb" generates the file "all_functional_derivatives". 
   As detailed in the paper, our computation requires heavy use of tensor strutures: rank 2, 4 and 6 trace anomalies
   for the 2, 3 and 4 point functions, rank 4, 6 and 8 countertems for the very same correlation functions. 
   All of them are obained by functionally differentiating scalars consisting of algebraic 
   combinations of the Riemann tensor, the Ricci tensor and the Ricci scalar
   The notebook starts by explaining the simplest functional derivatives of the metric tensor and goes on all the way up
   to anomalies counterterms and interaction vertices of the scalar with the background gravitational field, 
   introducing gradually more complex structures. 
   The second part of the notebook checks that the counterterms and the anomalies, which are computed non 
   perturbatively, obey all the constraints they are supposed to. This is needed to make us more confident about our 
   explicit calculations of the Green functions, provided that their divergent parts match the counterterms (they do indeed) 
   and that they pass the check of the trace Ward identies with the anomalies (they do as well).     

- "correlators_calculation.nb" explicitly computes the 2, 3 and 4 point functions, checks that they match the counterterms 
  computed in "functional_derivatives.nb" and stores them in 3 files: "T2_scalar", "T3_scalar" and "T4_scalar"

- The .jpg files in the "figures" folder are simply graphical representations of the diagrams computed in    
  "correlators_calculation.nb" and of the vertices computed in "functional_derivatives.nb", 
  which are loaded in the same notebooks just above the line of code computing each of them.
     
- The notebook "ward_identities.nb" checks the Ward identities for all of our 
  correlation functions; analytically for two and three-point, numerically for four-point.
  
  Have fun and please write me if you encounter any issues !
  
  Mirko Serino
