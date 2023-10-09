This Matlab code is a prototype for a 2D and 3D boundary element code to solve integral equations on non-manifold geometries.
It has been used to obtain the numerical results from <link here>.

To reproduce the figures of this paper, open Matlab in the folder FiguresScripts and run with appropriate parameters.
Note that the 3D BEM assembling routine requires the use of a mex file which calls a parallel C++ code.
The compilation of the mex file may depend on your specific configuration. If necessary, the call to bemAssembly 
can be replaced by slowBemAssembly, which bypasses the mex file and only executes pure Matlab code. 

The library uses:
- The Matlab toolboxes openMsh, openDom and openFem from https://github.com/matthieuaussal/gypsilab
This is code developed by François Alouges (https://scholar.google.com/citations?user=J5qUvVwAAAAJ&hl=fr) and Matthieu Aussal (https://fr.linkedin.com/in/matthieu-aussal-1708b245) to handle mesh and finite element integration in 2D and 3D.
- The Matlab toolbox GeneralizedMesh, which contains the "intrinsic inflation" algorithm which converts a msh object into a gen-mesh, a mesh structure designed for FEM and BEM in non-manifold geometries. 
This is based on https://www.sciencedirect.com/science/article/pii/S0168874X22001809
- A self-contained excerpt from the C++ code bemTools (https://github.com/xclaeys/bemtool) by Xavier Claeys (https://claeys.pages.math.cnrs.fr/), contained in hypersingular.cpp, quadrature.cpp 
It implements Duffy-type quadratures to treat the singular integrals in the boundary element method. 




 
