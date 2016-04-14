NLSAM datasets repository
-----------------

Synthetic and *in vivo* datasets used in the NLSAM paper, for which the main repo can be found [here](https://github.com/samuelstjean/nlsam/).
The synthetic data is based on an earlier version of [phantomas](https://github.com/ecaruyer/phantomas).

The data can be downloaded as zip files on the [releases](https://github.com/samuelstjean/nlsam_data/releases) page or cloned locally with
~~~
git clone https://github.com/samuelstjean/nlsam_data.git
~~~

Acknowledgments
-----------------

If you use the datasets provided therein, please make sure that you quote the following references in any publications:

~~~
St-Jean, S., Coupé, P., & Descoteaux, M.,
Non Local Spatial and Angular Matching: Enabling higher spatial resolution diffusion MRI datasets through adaptive denoising.
Medical Image Analysis, 32(2016), 115–130, 2016.
~~~

Please also credit (if applicable) the *in vivo* acquisition in the acknowledgments section of relevant papers as
~~~
Datasets were provided (in part) by the Centre d'imagerie moléculaire de Sherbrooke (CIMS)
and the Sherbrooke Connectivity Imaging Lab (SCIL), Université de Sherbrooke, Sherbrooke, Québec, Canada.
~~~

Synthetic data description
-----------------

The phantomas b1000 and phantomas b3000 folders contains the raw datasets that were used.
The masks folders contains everything needed for running a tractometer comparison in the proper folders.
The naming convention goes as follow

- hardi-scheme contains the bvals/bvecs used by the phantom, which is the same 64 gradient directions for both diffusion weighting.
- dwis.nii.gz is the noiseless ground-truth data to which noise was added afterward.
- SNR-(10, 15, 20 or 30) is the SNR of the dataset computed as SNR = mean(b0) / sigma,
    with mean(b0) computed inside white matter (see wm.nii.gz inside the masks folder) and sigma the noise standard deviation.
- coils-(1, 4, 8 or 12) defines the noise distribution as outlined in Eq. 6 of the paper.
- var-3 means that this dataset has a varying noise profile, which is SNR at the edges and SNR/3 near the center in a linear scale.

Note that not all datasets were used in the original paper, but are still provided here for interested users.

*In vivo* data description
-----------------

Two diffusion weighted scans and a T1 weighted scan of a healthy volunteer were acquired on a 3T Philips scanner.
A SENSE acceleration factor R = 2 (producing spatially varying Rician noise)
was used with a gradient strength of 45 mT/m and a 32 channels head coil. The following acquisition parameters were used :

For the high resolution dataset :

- 40 gradient directions at b = 1000 s/mm² + 1 b0 image at 1.2 mm voxel size
- TR/TE = 18.9 s / 104 ms
- Total acquisition time : 13 mins

For the standard resolution dataset :

- 64 gradient directions at b = 1000 s/mm² + 1 b0 image at 1.8 mm voxel size
- TR/TE = 11.1 s / 163 ms
- Total acquisition time : 12 mins

License
-----------------

All content is available under the [Creative Common Attribution license](https://creativecommons.org/licenses/by/4.0/), see [LICENSE](LICENSE) for more information.
