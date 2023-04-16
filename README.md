# PhysioMTL
## About
The work we are reproducing is from the 2022 paper “PhysioMTL: Personalizing Physiological Patterns using Optimal Transport Multi-Task Regression” (Zhu et al. 2022) [[1]](#1). The paper outlines Physiological Multitask-Learning, or PhysioMTL, a proposed method for improving heart rate variability (HRV) interpretation developed by resources at Apple Machine Learning Resource, Carnegie Mellon University, University of Illinois Urbana-Champaign, and University of Michigan. HRV is used to measure cardiovascular health and detect acute illnesses, but is too sensitive to irrelevant factors such as hydration, sleep, stress, etc.
(Acharya et al. 2006; European Society of Cardiology and Pacing Electrophysiology 1996) [[2]](#2). PhysioMTL attempts to denoise and normalize HRV data. Specifically, it learns to predict heart rate patterns at specific times of day based on demographics (age, gender, activity level, stress, etc).

What makes PhysioMTL interesting is that it utilizes multi-task learning (MTL), treating patients as tasks. It then uses Optimal Transport (OT) methods to efficiently match data to unseen patients and adjust for data gaps. Overall, this is an early use of multi-task learning in healthcare.

The specific claims of the original paper we are testing in this code are as follows. Each will be evaluated against the 5 baseline methods of Group Lasso, Multi-level Lasso, Dirty models, Multi-task Wasserstein, and Reweighted Multi-task Wasserstein.
* PhysioMTL trained on a large sample set (80\% of MMASH) outperforms (RMSE) the 5 baseline methods above
* PhysioMTL trained on a very small data set (20\% of MMASH) outperforms (RMSE) the 5 baseline methods above
* PhysioMTL holds a more stable (lesser range) accuracy than the 5 baseline methods above across many data set training size (20%, 40%, 60%, and 80% of MMASH)

## Instructions
To recreate our results, run the included PhysioMTL.ipynb within a Jupyter environment. The provided code will automatically download, process, train, and test the MMASH dataset and report results that support the claims presented in the paper. 

## References
<a id="1">[1]</a> 
Zhu, Jiacheng et al. (July 2022). 
“PhysioMTL: Personalizing Physiological Patterns using Optimal Transport Multi-Task Regression”. In: Proceedings of the Conference on Health, Inference, and Learning. Ed. by Gerardo Flores et al. Vol. 174. Proceedings of Machine Learning Research. PMLR, pp. 354–374. 
URL: https://proceedings.mlr.press/v174/zhu22a.html.

<a id="2">[2]</a>
Acharya, Rajendra U. et al. (2006). “Heart Rate Variability: A Review”. In: Medical and Biological Engineering and Computing 44.12, pp. 1031–1051.
