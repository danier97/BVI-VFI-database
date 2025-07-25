# BVI-VFI: A Video Quality Database for Video Frame Interpolation

### [Duolikun Danier](https://danier97.github.io/), [Fan Zhang](https://fan-aaron-zhang.github.io/), [David Bull](https://david-bull.github.io/)
### IEEE Transactions on Image Processing (TIP)

[Paper](https://doi.org/10.1109/TIP.2023.3327912) | [Database download](https://forms.office.com/e/gtKpYriSMJ) | [arXiv](https://arxiv.org/abs/2210.00823v3)


## Updates

**[2023.10.21]** We added DMOS scores obtained via the subject screening process recommened by [ITU-T P.910](https://www.itu.int/ITU-T/recommendations/rec.aspx?rec=15005&lang=en). See the Description section below for details.

## TL; DR
- A video database with subjective quality labels was collected.
- Analysis on quality labels reveals that
    - Recent deep learning-based VFI methods have a clear advantage over simple frame repeating and averating, but the performance gap narrows at frame rate increases.
    - Simple frame repeating and averating can outperform DL methods on dynamic textures (rapid and irregular motion).
    - Motion magnitude and complexity jointly impacts VFI difficulty.
    - Higher spatial resolution also makes VFI more challenging.
- 33 existing image/video quality assessment methods were benchmarked, and best performance (SRCC=0.7) was achieved by FAST.
- There is a need for a better quality evaluator for VFI, and the proposed database can be used for development and benchmarking of them.


## Downloading the database

Please fill in this [registration form](https://forms.office.com/e/gtKpYriSMJ) to get access to the download link.

## Description

### Videos
The BVI-VFI database contains 108 reference and 540 distorted sequences, as well as the differential subjective scores for all the distorted videos.
The .mp4 files contained are compressed with H.264 (libx264) under lossless mode (crf=0). The naming of the files are as follows:
```
<seq name>_<spatial resolution>_<frame rate>_<VFI method>.mp4
```

Files ending with "_GT.mp4" are the reference sequences.

### Subjective data
We provide raw subjective data and post-processed DMOS scores obtained according to two different standards: ITU [BT-500](https://www.itu.int/rec/R-REC-BT.500) and [P.910](https://www.itu.int/ITU-T/recommendations/rec.aspx?rec=15005&lang=en). These subjective data are provided in .json format.

#### P.910
- `all_data_raw.json`: raw scores collected from subjects, including scores given to both reference and distorted videos.
- `all_dmos_p910.json`: the DMOS values obtained following the P.910 subject screening method (see the standard and paper for more details).
- `all_dmosstd_p910.json`: the standard deviations of the DMOS obtaiend via P.910.

#### BT-500
- `all_diff_raw.json`: the differential scores calculated for all the judgements of all users. Each score = (score assigned by the participant to current reference) - (score assigned by the participant to current distorted sequence).
- `all_z_scores.json`: the differential scores normalised over the scores given by each user (see paper for more details).
- `DMOS_XXXXp.json`: the DMOS scores computed for each distorted sequence.


## Copyright disclaimer
The sequences contained in the BVI-VFI dataset are obtained from various sources, including 
 - [BVI-HFR dataset](https://data.bris.ac.uk/data/dataset/k8bfn0qsj9fs1rwnc2x75z6t7)
 - [LIVE-YT-HFR dataset](https://live.ece.utexas.edu/research/LIVE_YT_HFR/LIVE_YT_HFR/index.html)

This database has been compiled by the University of Bristol, Bristol, UK. All intellectual property rights remain with the University of Bristol. The dataset should only be used for academic purpose. This copyright and permission notice shall be duplicated whenever the data is copied. The University of Bristol makes no warranties with respect to the material and expressly disclaims any warranties regarding its fitness for any purpose. Unless the above conditions are agreed to by the recipient, no permission is granted for any use and copying of the data. By using the database and sequences, the user agrees to the conditions of this copyright and disclaimer.


## Citation
```
@article{danier2023bvi,
    title={BVI-VFI: A Video Quality Database for Video Frame Interpolation},
    author={Danier, Duolikun and Zhang, Fan and Bull, David R},
    journal={IEEE Transactions on Image Processing},
    year={2023},
    publisher={IEEE}
}
@inproceedings{danier2022subjective,
    title={A subjective quality study for video frame interpolation},
    author={Danier, Duolikun and Zhang, Fan and Bull, David},
    booktitle={2022 IEEE International Conference on Image Processing (ICIP)},
    pages={1361--1365},
    year={2022},
    organization={IEEE}
}
```
