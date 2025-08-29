Dear Author(s):

We write to you in regard to the manuscript # MRM-24-25421 entitled "High-Resolution and Motion-Robust Diffusion-Weighted Imaging with Self-Gated Self-Supervised Unrolled Reconstruction," which you submitted to Magnetic Resonance in Medicine.

Your manuscript has been reviewed by Referees who are knowledgeable about this topic. Unfortunately, in view of the overall comments and scores found below, we must reject your manuscript at this time. Despite raising a number of major issues, the Referees did find value in your manuscript and provide guidance about how it can be improved. Consequently, if you can provide a substantially revised manuscript that addresses the concerns of the Referees and Editors, we invite you to resubmit this work to Magnetic Resonance in Medicine. In order for the resubmitted manuscript to be acceptable for Magn Reson Med, however, some of its scores will need to improve significantly. Additional explanation is provided in the editorial comment below.

The resubmission would be treated as a new manuscript and receive a new submission date. Please reference the current manuscript number MRM-24-25421 in your cover letter. In general, the resubmission may be reviewed by the same Referees. Please resubmit your manuscript without revision markings. Instead, we ask that you provide a point-by-point response to the Referees in a separate file, and submit that file as supplemental material for review. We should mention that as an alternative to a resubmission to Magnetic Resonance in Medicine, at this time you are free to submit your work to a different journal instead, should you prefer.

Wiley Editing Services Available to All Authors
Should you be interested, Wiley Editing Services offers expert help with manuscript, language, and format editing, along with other article preparation services. You can learn more about this service option at www.wileyauthors.com/eeo/preparation. You can also check out Wiley’s collection of free article preparation resources for general guidance about writing and preparing your manuscript at www.wileyauthors.com/eeo/prepresources.

Thank you for considering Magnetic Resonance in Medicine for the publication of your research.

Sincerely,

Shanshan Wang, , Deputy Editor
Peter Jezzard, Ph.D. (he/him), Editor-in-Chief

Magnetic Resonance in Medicine
mrm@ismrm.org



Editor's Comments to the Author:
Thanks for submitting to Magn Reson Med. Firstly, apologies for the delay in getting you an outcome – we struggled to identify willing reviewers. Finally, though, we found two expert referees. As you can see, although there is potential interest from them in the study there are substantial issues raised by both. As such I regret that we must return the current version of the manuscript to you. We would allow a future resubmission if you wished to undertake the considerable work outlined by the reviewers, but we would need to see a substantial improvement in reviewer enthusiasm and accompanying scores. Alternatively, you would be at liberty at this juncture to submit elsewhere.


Deputy Editor: Wang, Shanshan
Comments to Author:
Dear Authors,

Thank you for your submission. The paper has been reviewed by two experts, with one recommending rejection and the other suggesting major revisions. The key concerns raised are as follows:

The baseline navigated method does not appear to work as expected.
There is no comparison with other state-of-the-art (SOTA) methods.
The results validation is primarily qualitative and subjective.
Given these issues, we are unable to consider the current version of your manuscript further unless you are willing to make substantial revisions to address these concerns. Please be aware that, should you choose to resubmit, the revised manuscript will typically be sent to the same reviewers.

Thank you again for your submission, and we appreciate your understanding.

Best regards,



Referee(s)' Comments to the Author:

Referee: 1

Comments to the Author
This manuscript presents a deep learning-based reconstruction method for high-resolution multi-shot DWI. Specifically, the authors employ ADMM unrolling with a network-learned regularization to enable multi-shot DWI reconstruction while mitigating artifacts caused by shot-to-shot phase variations. They report achieving 0.7 mm isotropic resolution DWI on a 7T scanner with good image quality. While the proposed approach is promising, I have several major concerns regarding the presentation and validation of the method.
1. The current review of reconstruction methods in the Introduction feels somewhat mixed. Methods for motion-phase correction (e.g., MUSSELS) and k-q joint reconstruction (e.g., DAE) are discussed together, which might obscure their distinct purposes. I suggest that the authors introduce these methods separately to help readers better understand the core objectives of each category.
2. Regarding the forward model A used in the proposed ADMM unrolling method (Eq. 2 and Algorithm 1), what was specifically used as the motion phase map Φ? Was it derived from MUSE? The authors note: “However, it (MUSE) requires small undersampling factors per shot and fully sampled DWI acquisition assembling all shots. Alternatively, undersampled DWI acquisition can be enabled via the acquisition of navigators for shot phase estimation.” This gives the impression that navigator-based phase correction should outperform MUSE. However, the results in Fig. 4 suggest otherwise, which seems contradictory.
3. The navigator-based phase correction shown in Fig. 4 appears overly artifacted. The authors attribute this to increased scan time leading to greater sensitivity to inter-shot motion: “The main reason for these artifacts is that the acquisition of navigators increases the total scan time, resulting in higher sensitivity to accidental inter-shot motion.” However, I find this explanation unconvincing. Since this is a retrospective experiment, the effective scan time for both navigated and self-gated acquisitions should be identical, meaning that the subject would experience the same motion in both cases. The inclusion of a navigator introduces a second echo, but since motion primarily affects the phase during diffusion encoding, the phase should remain static after diffusion encoding, allowing accurate phase correction using the navigator. It seems more likely that the artifacts arise from errors in navigator implementation. To clarify this, I recommend that the authors present the navigator phase data and compare it with the MUSE-estimated phase.
4. Due to the failure of the navigator-based method, a reliable reference for comparison is lacking. Consequently, many of the presented results rely on subjective, qualitative assessments. This may weaken the overall impact of the manuscript. To strengthen the validation, I recommend acquiring a high-quality reference dataset and/or conducting simulations with known ground truth, which would enable more objective and quantitative evaluation.
5. The authors present only raw DWIs, which makes it difficult to evaluate the overall quality of the acquired diffusion datasets, particularly in the absence of a reference. I suggest performing additional diffusion analyses, such as DTI, to provide more convincing evidence of the proposed method’s advantages over existing approaches (e.g., LLR).
6. While the authors compare slice-by-slice and single-slice training in Fig. 3, this comparison remains largely qualitative. The single-slice training result appears to exhibit diminished diffusion contrast, which was not reflected in the signal plot—likely because the selected voxel did not fall within a region of strong diffusion contrast. A more compelling evaluation could be plotting the signal variance across diffusion encoding directions to assess whether single-slice training introduces angular smoothing.

Referee: 2

Comments to the Author
This paper proposes a self-supervised unrolled reconstruction algorithm for high-resolution and motion-robust diffusion-weighted imaging. Experimental results on a clinical 7T scanner demonstrate the effectiveness of the proposed method. Some issues remain to be addressed:

Method:

1、The authors partitioned the sampling masks into 12 repetitions. Are the masks consistent across these repetitions? Each mask is subdivided into three disjoint subsets. What advantages does this approach offer compared to partitioning the masks into only two disjoint subsets?

2、Dividing the sampling masks into three disjoint subsets reduces the amount of original effective data input for each part of the network. Does this approach allow the network to learn the overall data distribution effectively? Have the authors considered this potential limitation?

3、The authors proposed two distinct training strategies. I want to know whether the model was trained on a subset of data from a single volunteer and tested on another subset from the same volunteer.

4、I would appreciate it if the authors could clarify the aspect in which motion robustness is manifested. Is it achieved through phase shift correction, or does it involve another technique?

Experiments:

1、The experiment utilized data from only three volunteers, representing a very small sample size.

2、Would it be possible to include deep learning-based self-supervised methods, such as SSDU, and multi-mask SSDU, as additional comparison methods?

3、In Figure 4, the authors assert that the unrolled ADMM offers an advantage in preserving clear tissue boundaries; however, the region marked by the red arrows in the figure is not clearly defined.

4、The experiments in this paper are conducted using data from a single volunteer. Did the authors attempt to train on one part of the volunteer’s data and test on another part from the same volunteer?

5、In Figure 7, could the authors clarify why the validation loss is lower than the training loss in the early stages of training?



Referee(s)' Responses to the Questionnaire:

Referee: 1
Originality of content: 3 – Good

Referee: 2
Originality of content: 3.5

Referee: 1
Soundness of conclusions: 2 – Fair

Referee: 2
Soundness of conclusions: 3.5

Referee: 1
Importance (significance of results, potential implication on other work, reader interest): 3.5

Referee: 2
Importance (significance of results, potential implication on other work, reader interest): 3.5

Referee: 1
Quality (quality of methodology and data, clarity of presentation): 2 – Fair

Referee: 2
Quality (quality of methodology and data, clarity of presentation): 3 – Good

Referee: 1
Is the manuscript in the appropriate category? : Yes

Referee: 2
Is the manuscript in the appropriate category? : Yes

Referee: 1
If no, please indicate appropriate category:

Referee: 2
If no, please indicate appropriate category:

Referee: 1
Can manuscript be shortened without compromising intended message? : No

Referee: 2
Can manuscript be shortened without compromising intended message? : No

Referee: 1
Accuracy (are there substantive errors?) : No

Referee: 2
Accuracy (are there substantive errors?) : No

Referee: 1
Do the figures, tables, abstract, and overall organization adhere to the MRM Style Guide? (If not, please elaborate in the written comments): Yes

Referee: 2
Do the figures, tables, abstract, and overall organization adhere to the MRM Style Guide? (If not, please elaborate in the written comments): Yes

Referee: 1
Needs linguistic editing for English?  : No

Referee: 2
Needs linguistic editing for English?  : No

Referee: 1
Is there a figure that justifies consideration for MRM’s cover:

Referee: 2
Is there a figure that justifies consideration for MRM’s cover:


Referee: 1
Please indicate if you think that the authors have gone to special efforts to provide data or code in support of MRM’s Reproducible Research goal: Yes

Referee: 2
Please indicate if you think that the authors have gone to special efforts to provide data or code in support of MRM’s Reproducible Research goal: Yes

Referee: 1
Is MRM the appropriate journal? : Yes

Referee: 2
Is MRM the appropriate journal? : Yes

Referee: 1
If no, please suggest an alternative journal:

Referee: 2
If no, please suggest an alternative journal: