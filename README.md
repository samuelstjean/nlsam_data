# nlsam datasets repository

Synthetic datasets used in the NLSAM paper, for which the main repo can be found [here](https://github.com/samuelstjean/nlsam/).
The phantom is based on an earlier version of [phantomas](https://github.com/ecaruyer/phantomas)
The masks folders contains everything needed for running a tractometer comparison in the proper folders.

The phantomas b1000 and phantomas b3000 folders contains the raw datasets that were used. The naming convention goes as follow

+ hardi-scheme contains the bvals/bvecs used by the phantom, which is the same 64 gradient directions for both diffusion weighting.
+ dwis.nii.gz is the noiseless ground-truth data to which noise was added afterward.
+ SNR-(10,15,20 or 30) is the SNR of the dataset computed as SNR = mean(b0) / sigma, with mean(b0) computed inside white matter (see mask) and sigma the noise standard deviation.
+ coils-(1,4,8 or 12) defines the noise distribution as outlined in Eq. 6 of the paper.
+ var-3 means that this dataset has a varying noise profile, which is SNR at the edges and SNR/3 near the center in a linear scale.

Note that not all datasets were used in the original paper, but are still provided here for interested users.

If you would like access to the in-vivo diffusion scan, feel free to contact me.
