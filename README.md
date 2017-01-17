# kmer_models
This repository contains predictive kmer models for development use. Each folder contains a set of template and complement models and is named in the format

`<pore>_<bias_voltage>_<speed>_<kmer_length>[_RNA]`

e.g. `r9.2_180mv_250bps_6mer`

There will usually be one template model and two complement models. The two complement models correspond to "nonuplifted" and "uplifted" populations ("pop1" and "pop2" respectively).

Each model is a tab-delimited text file containing seven columns. These models assume that the current levels for each kmer can be approximated using a Gaussian distribution and the corresponding signal noise can be approximated using an inverse Gaussian distribution.

1. **kmer** The kmer being modelled.
2. **level_mean** The mean of a Gaussian distribution representing the current observed for this kmer.
3. **level_stdv** The standard deviation of the above Gaussian distribution of observed currents for this kmer.
4. **sd_mean** The mean of an inverse Gaussian distribution representing the noise observed for this kmer.
5. **sd_stdv** The standard deviation of the above inverse Gaussian distribution of noise observed for this kmer.
6. **ig_lambda** The lambda parameter for the above inverse Gaussian distribution of noise observed for this kmer.  
   (so `sd_stdv == sqrt(sd_mean ^ 3 / ig_lambda`). See [Wikipedia](https://en.wikipedia.org/wiki/Inverse_Gaussian_distribution) for more info.
7. **weight** Used internally for model training purposes.

## RNA kmer models

Note that RNA kmer models currently have uracil labelled as thymine, so that it looks like DNA. This is in keeping with the present output format of the event table in basecalled fast5 files, though it may change in future.
