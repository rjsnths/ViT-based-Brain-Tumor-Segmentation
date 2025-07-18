# ViT-based-Brain-Tumor-Segmentation

CNN is good at extracting local features and recognizing patterns, while ViT is strong at learning global relationships within an image. Based on these differences, we specifically identify the strengths and weaknesses of the two models in MRI images and compare how effective each model is at detecting brain tumors. In addition, Transformer has shown excellent performance in NLP, but its potential in image analysis, especially medical image analysis, is still in its early stages. This study aims to examine what advantages ViT has over existing CNN-based techniques, and especially how useful it is in clinical applications.

-----------------------------------------------------------------
# DataSets

Before the experiment, the BraTS dataset provided in the existing .nii format was preprocessed into a .h5 file format based on slices. The shape of the image is (240 x 240 x 4) and it is a form in which four sequences T1CE, T1N, T2W, FLAIR are stacked as channels.
The shape of the mask is (240 x 240 x 5) and it has five channels including four labels representing different types of brain tumors Enhancing Tumor, Non-Enhancing Tumor, Cystic Component, Edema and a backgroud.\
\
\
Patient Ids ranged from 1 to 266, and 100 slices were used for each patient, for a total of 26,600 slices used for learning.
\
\
All Train conditions were set as follows.\
[Epoch : 280, Batch Size : 32, Learning rate : 10<sup>-4</sup>, Loss func : BCEWithLogitsLoss, Optimizer : AdamW]
\
\
This is the Ground Truth we need to predict.

<img width="1359" height="439" alt="스크린샷 2025-02-03 143635" src="https://github.com/user-attachments/assets/528b8146-5f6d-4ca5-898e-6382b5d7e1e9" />






# Results

### 1. 2D CNN
<img width="1363" height="436" alt="스크린샷 2025-02-01 205737" src="https://github.com/user-attachments/assets/e3b3d75c-40f3-465b-8a39-2f95461ab0b0" />
<img width="400" height="250" alt="스크린샷 2025-02-01 205451" src="https://github.com/user-attachments/assets/501411f0-9d17-4414-8280-cea3e427da97" />



### 2. ViT
<img width="1356" height="434" alt="스크린샷 2025-02-03 143202" src="https://github.com/user-attachments/assets/fa449296-cc99-4d73-98c0-fc3b60a71442" />
<img width="400" height="250" alt="스크린샷 2025-02-03 143058" src="https://github.com/user-attachments/assets/21398e1b-ee4a-4d5d-a945-40e5e9d4be67" />





### 3. Swin Transformer
<img width="1365" height="448" alt="스크린샷 2025-02-03 143549" src="https://github.com/user-attachments/assets/1c68fa7e-35d2-43b5-8d3c-0664a773cdcb" />
<img width="400" height="250" alt="스크린샷 2025-02-03 143456" src="https://github.com/user-attachments/assets/ee261161-e724-447a-904f-24c86f3bcdf7" />






# Conclusion
The loss of Swin Transformer is <ins>reduced by about 0.27 compared to 2D CNN</ins>, and the predicted mask is also more similar to the correct answer. Therefore, we belive that the useof ViT in the targeted filed of Brain Tumor Segmentation has achieved meaningful results as it has succeeded in stable progress and performance improvement.

