# 4 EMT correlation function

This is a collection of the files I developed in order to perform and test the explicit calculation of the 4-point function
of the stress energy tensor in a free conformal field theory in 4 spacetime dimensions.

Just load them up and run them in Mathematica (version 10.1 or higher). 

Calculations of the 2 and 3 point functions are detailed as well, in order to prvide a framework in which the reader can 
familiarize with the tools employes and with the ideas underpinning the calculations and their tests, if she/he is not yet 
familiar with them.

Plase note that some of the calculations can be quite time consuming and that the numerical checks of the Ward identities for 
the 4 point function requires your computer to have least 25 GB of memory at its disposal in order not to crush.

Here follows a concise description of the scope and purpose of each notebook: 

1 - The noteook "tensor_bases_generation.nb" GENERATES the 4 files "tensmom#rank##". 
    As the name suggests, the tensors in each of these files 
    span a complete basis of tensors which are rank ## products of the metric tensor and # independent momenta. They are 
    needed to check the Ward identities for the 3 and 4 point correlation functions.
    
2 -  "all_functional_derivatives_computed.nb" generates "all_functional_derivatives". 
     As detailed in hte paper, our computation requires heavy use of tensor strutures: rank 2, 4 and 6 trace anomalies
     for the 2, 3 and 4 point functions, rank 4, 6 and 8 countertems for the very same correlation functions. 
     All of them are obained by functionally differentiating scalars consisting of combinations of algebraic 
     combinations of the Riemann tensor, the Ricci tensor and the Ricci scalar.
     The notebook starts by explaining the simplest functional derivatives of the metric tensor and goes on all the way up
     to anomalies counterterms and interaction vertices of the scalar with the background gravitational field, 
     introducing gradually more complex structures. 
    
3 - "all_functional_derivatives_checked.nb" checks that the counterters and the anomalies, which are compted ina. purelynon 
     perturbative way, obey all the constraints they are supposed to. This is needed to make us more confident about our 
     explicit calculations of the Green functions, provided that their divergent parts match the counterterms (they do indeed) 
     and that they pass the check of the trace Ward identies with the anomalies (they do as well).     

4.1- "correlators_calculation.nb" explicitly computes the 2, 3 and 4 point functions, checks that they match the counterterms 
    computed in "all_functional_derivatives_computed.nb" and stores them in 3 files: "T2_scalar", "T3_scalar" and "T4_scalar"

4.2- The folder "diagrams" simply contains graphical representations of the diagrams computed in "correlators_calculation.nb", 
     which are loaded in the sme notebook next to the lines computing the corresponding diagrams.
     
5 - The notebooks "Ward_identities_2T_and_3T.nb" and "Ward_identities_4T.nb" chekc the Ward identities for all of our 
    correlation functions. The first one does so analytically; the second resorts to a numerical check.
