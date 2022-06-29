# Phase-AttenuationExtraction_PBPCXI_Allooetal2022
This is an automated PB-PCXI algorithm capable of extracting the X-ray attenuation and refraction components of the complex refractive index of distinct materials within an unknown sample.

This script is based off the publication “Alloo, S.J., Paganin, D.M., Morgan, K.S., Gureyev, T.E., Mayo, S.C., Mohammadi, S., Lockie, D., Menk, R.H., Arfelli, F., Zanconati, F., Tromba, G., and Pavlov, K.M. 2022. Tomographic phase and attenuation extraction for a sample composed of unknown materials using x-ray propagation-based phase-contrast imaging. _Optics Letters_, 47(8), pp.1945-1948.”, which is furthermore published in the XRM2022 conference proceedings, where a link to this repository was provided. Please ensure appropriate referencing and acknowledgement is made to this work when you use this script within your own.

This script is well-commented and therefore should be simple to use. For the direct equations used in this script, please refer the publication listed above. This approach can be used for any phase-contrast X-ray imaging (PCXI) data, for which you have a computed-tomographic reconstruction and there is residual phase contrast at material boundaries. We have applied it to both propagation-based and speckle-based PCXI data, for both synchrotron X-ray sources and conventional X-ray tube sources (seen in laboratories), and it works well! 

The script consists of two functions: 
1)	Defines the error function model 
2)	A function which calculates the true value of \gamma = \deta / \beta for the inputted interface 
The second function requires 6 input variables: 
-	filepath
-	gamma_guess
-	sod
-	odd
-	wavelength
-	det_voxel
Definitions for each of these variables can be found within the script. When using PCXI data collected using a conventional X-ray tube, the wavelength can be replaced with the wavelength of the effective energy of the polychromatic X-ray spectra (typically, 0.5 or 0.33 of the kVp). 

The true value of \gamma = \deta / \beta, as well as the relative \deta and \beta for the interface are printed within the script. A unique value for \deta for each composite material can be determine by establishing a set of linear equations using the definition of \gamma for an interface. Although this isn’t performed directly in the script, it is easy to do, and a further explanation of this is provided in both publications. If you have any further questions on how to do this, please contact S. J. Alloo on samantha.alloo@pg.canterbury.ac.nz. 
