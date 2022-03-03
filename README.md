# TIE_based_on_FFT_method
MATLAB code for solving TIE (Transport-of-intensity equation) based on FFT method for phase retreival.

Author: Semin Cheon. M.D/Ph.D integrated course. MDAIL(KAIST).
          chsm0338@kaist.ac.kr

This script calculates Transport-of-Intensity Equation(TIE) by solving
inverse laplacian using FFT method.

- References:
1. C. Zuo, J. Li, et al, Elsvier. volume 135 (2020).
2. J. Schmalz, T. Gureyev and D. Paganin, Phys. Rev. A. 84, 023808
(2011).
3. D. Paganin and K. A. Nugent, Phy. Rev. Lett. 80, 2586 (1998).

- Function:
 [ Phase_Retrieval ] = TIE_FFT( dIdz, I0, Wavelength, tikhonov_Para, Threshold_Real, Pixel_Size )

          Input - dIdz: Imagederivate calculated by Overfocus and Underfocus images
           - I0: Onfocus image
           - Wavelength: wavelength of the light source
           - tikhonov_Para: Small constant for two purposes;
              1. To avoid zero-division problem in fourier space during FFT
                     calculation
              2. To remove low-frequency noise
          - Threshold_Real: Small constant To avoid zero-division problem in
            real space
          - Pixel_Size: A pixel size of the images ( Needed for defining sampling frequency of images)

          Output - Phase_Retrieval: Phase image by solving TIE using FFT method

-   TIE  

           eq:             Div( I0 * Grad(phase) ) = -k * dI/dz
          applied eq:     Div(Grad(phase)) = -k * dI/dz - Grad(I0)

(※ RHS of the eq is on the in-plane region st, operators in the RHS are also in-plane operators)
 
- Computational approach:
           - Please refer Eq(50) from the paper: C. Zuo, et al, Elsvier. volume 135 (2020).

- Last modified: 2022/02/15 (Y/M/D) - Now explanations of the codes are included 
