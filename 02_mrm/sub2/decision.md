09-Oct-2025

Dear Author(s):

Manuscript # MRM-25-26288 entitled "High-Resolution Diffusion-Weighted Imaging with Self-Gated Self-Supervised Unrolled Reconstruction," which you submitted to Magnetic Resonance in Medicine, has been reviewed. Comments about your manuscript can be found at the end of this letter.

Thank you for submitting your manuscript to Magn Reson Med. It was reviewed by Referees who are knowledgeable about this topic, and was well-received. As an important step towards publication, we are very pleased to invite you to submit a revised version that thoroughly addresses the Referees’ concerns. Additional guidance is provided in the editorial comment.

We believe that it is the obligation of the authors to be responsive to the comments of the reviewers and editors. We also expect each point to be addressed, including improvements in scientific methods, if requested. In the case where you, as authors, fundamentally disagree with a review point, we ask that you provide a rebuttal. Magn Reson Med generally will no longer support more than two opportunities for revision, so please consider the comments carefully. We would like to provide you 30 days from the date of this email to submit your revision and response. If you will need additional time, contact the editorial office at mrm@ismrm.org before the 30-day period elapses. Please carefully read and follow the instructions describing electronic submission procedures to avoid delays.

The mission of Magn Reson Med includes promoting reproducible research. Whenever applicable, the journal strongly encourages authors to facilitate the reproducibility of their published research by making the computer code used in their simulations, image reconstruction, analysis, statistical analysis, etc. publicly available. Please consider this carefully during the revision of your manuscript. The sharing of anonymized image sets, anonymized raw k-space sets, numerical phantoms, etc. is also encouraged. For examples, please see https://www.ismrm.org/MR-Hub, and for more information see the Magn Reson Med Authors’ Guidelines.

Our journal is currently transitioning to Wiley’s Research Exchange submission portal. Please read these instructions carefully.

If you submitted your manuscript through our Research Exchange site, you will see a link below to submit your revised manuscript: https://submission.wiley.com/submissionBoard/1/d9d3bd30-9320-4191-a7db-f45df8965854/current (If no link appears, follow the instructions in the next paragraph.)

Click on the link or go to wiley.atyponrex.com/journal/MRM. Sort by journal and submission status to locate this manuscript, then click the “Revise submission” button to submit your revision. You will be able to respond to the reviewer comments when asked to “Upload your Author Response”. All supplementary and additional files will be carried over when you submit a revised manuscript. You may be required to provide additional files at the revision stage.

If you submitted your manuscript through ScholarOne, please use this link to submit your revised manuscript: *** PLEASE NOTE: This is a two-step process. After clicking on the link, you will be directed to a webpage to confirm. ***

https://mc.manuscriptcentral.com/mrm?URL_MASK=901b51cf7f7e4f7c97ea89b8d27bbe08 Click on the link or go to https://mc.manuscriptcentral.com/mrm and enter your Author Center, where you will find your manuscript title listed under "Manuscripts with Decisions." Under "Actions," click on "Create a Revision”. You will be able to respond to the comments made by the reviewer(s) in the space provided. Your original files are available to you when you upload your revised manuscript. Please delete any redundant files before completing the submission.

This journal offers a number of license options, information about this is available here: https://authorservices.wiley.com/author-resources/Journal-Authors/licensing/index.html. All co-authors are required to confirm that they have the necessary rights to grant in the submission, including in light of each co-author’s funder policies. For example, if you or one of your co-authors received funding from a member of Coalition S, you may need to check which licenses you are able to sign.

Once again, thank you for submitting your manuscript to Magnetic Resonance in Medicine. We look forward to receiving your revision soon.

Sincerely,

Shanshan Wang, , Deputy Editor
Peter Jezzard, Ph.D. (he/him), Editor-in-Chief

Magnetic Resonance in Medicine
mrm@ismrm.org



Editor's Comments to the Author:
Thanks for resubmitting to Magn Reson Med. Your new manuscript went back to the original reviewers who both agree that it has been improved. However, there are still some remaining issues and corrections that are requested. We invite a further minor revision that seeks to address the remaining points that have been made. You may also wish to take this opportunity to ensure that your reference list is up to date and captures any recent relevant papers.

Deputy Editor: Wang, Shanshan
Comments to Author:
Dear authors,
The paper has been reviewed by two experts, who still have some concerns. Please properly address them. Many thanks.



Referee(s)' Comments to the Author:

Referee: 1

Comments to the Author
This manuscript's application of an unrolled ADMM network with a zero-shot approach for DWI reconstruction is an interesting contribution, particularly the model's demonstrated generalizability across slices. However, there are several aspects that would benefit from further consideration and revision.
Regarding the manuscript's academic writing and presentation, there are several opportunities for enhancement.
1. In the introduction, the presentation of related works could be strengthened by more clearly articulating the specific limitations of existing unrolled and self-supervised methods, which would better motivate the proposed solution.
2. In the Method section, a couple of refinements could enhance clarity. The flowchart for Algorithm 1 is somewhat lengthy; streamlining it to highlight only the most essential steps would make it more accessible. Additionally, the self-supervised learning strategy should be supplemented with rigorous mathematical formulas to formally define the process.
3. Finally, to substantiate the claim of faster reconstruction, the manuscript should include a direct, quantitative comparison of reconstruction times against competing methods.
There a few points require clarification in the manuscript.
1. In Section 2.3, could you provide more specific details regarding the ADMM unrolling implementation? For example, information on the architecture of the ResNet used, such as the number of layers, would be very helpful.
2. Figure 9 suggests that λ from Equation (3) is a learnable parameter. Is the penalty parameter ρ in the same equation also treated as learnable, or is it a fixed value?
3. In the ablation study described in Section 3.1, you compare the reconstruction results of MUSE, LLR, and ADMM unrolling for both 4-shot and 2-shot acquisitions. Could you clarify how this comparison constitutes an ablation study? An ablation study typically analyzes the impact of removing specific components of the proposed model, whereas this seems to be a performance comparison across different methods under varying conditions.

Referee: 2

Comments to the Author
Thank you to the authors for addressing some of my previous concerns. However, the current version still does not meet the requirements for publication, and several issues remain to be resolved:

1、A major limitation of the proposed method is that it requires training a separate model for each subject, which significantly restricts its applicability. I suggest that the authors provide detailed training and testing times. Alternatively, they could evaluate whether a model trained on one subject’s data can be generalized to other subjects.

2、In Table 3, it appears that the fully sampled data are different across methods. What is the rationale for this design choice? Why are the fully sampled datasets not identical?

3、In Figure 9, is the λ parameter the same as the λ used in Algorithm 1? Their initial values seem to be inconsistent.

4、On page 9, line 50, the authors state: “However, we also observed that the self-gated …… (e.g., the 0.5×0.5×2.0 mm³ DWI data with an acceleration of 15×2 per shot).” How was the 0.5×0.5×2.0 mm³ dataset acquired? The manuscript does not explain.

5、For retrospective experiments, I recommend including reference data for comparison.

6、Please check the consistency of abbreviations in the manuscript, such as “selfgated” vs. “self-gated,” and standardize them accordingly.



Referee(s)' Responses to the Questionnaire:

Referee: 1
Originality of content: 3.5

Referee: 2
Originality of content: 3.5

Referee: 1
Soundness of conclusions: 3.5

Referee: 2
Soundness of conclusions: 4 – Very good

Referee: 1
Importance (significance of results, potential implication on other work, reader interest): 4.5

Referee: 2
Importance (significance of results, potential implication on other work, reader interest): 3.5

Referee: 1
Quality (quality of methodology and data, clarity of presentation): 3.5

Referee: 2
Quality (quality of methodology and data, clarity of presentation): 4 – Very good

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
If so, please specify: Fig. Number:

Referee: 2
If so, please specify: Fig. Number:

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