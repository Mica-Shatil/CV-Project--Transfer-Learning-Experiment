# READ_ME_FIRST

## Transfer Learning Using MobileNetV3

**Authors**: M.S., V.P.

### Abstract

Transfer learning is a popular machine learning technique that uses knowledge gained from training a model on one task to help learn a different but related task. This approach is particularly beneficial when limited data is available for the target task.

This project explores the effectiveness of transfer learning using the MobileNetV3 model across various image classification domains, including Pokemon, flowers, and Bollywood celebrities. The main objective is to assess how well the pre-trained MobileNetV3 model can generalize to new and unrelated datasets, as well as the impact of different amounts of training data and epochs on classification accuracy. We utilize the initial layers of the pre-trained MobileNetV3 model as a feature extractor, modifying only the final classifier layer for the specific task.

**Hypotheses**:
1. With increasing epochs and training data, model performance will improve.
2. Models trained with transfer learning will show significant accuracy improvements over models with randomly initialized parameters at each epoch.

Notebooks for each task contain detailed information and conclusions regarding the application of transfer learning to each domain.

### Team Members and Contributions

*Both teammates collaborated on designing functions and procedures for all datasets, and jointly participated in topic and dataset research. The `train` and `test` functions were developed collaboratively and modified for each dataset.*

### Code Libraries

- **datasets**: HuggingFace's `datasets` library was used to load and stream datasets, especially useful for extracting small subsets from large datasets. We used version 2.15.0, which can be installed via `pip install datasets`.

---

### Summary

#### Oxford Flowers
Experiments with the Oxford Flowers dataset showed a performance boost with increasing epochs and training data. Transfer learning outperformed random initialization, achieving a maximum accuracy increase from 41% to 85% and an average increase from 10% to 56%. This highlights the utility of pretrained CNN parameters for standardized image filtering in early layers. Transfer learning models displayed logarithmic growth in training accuracy, while models with random initialization improved linearly, roughly 10% per increment. Interestingly, adding 30-40 examples had minimal impact on transfer learning models' performance. The larger MobileNet model did not perform as well, underscoring that larger models may not always yield better results and take longer to train.

#### Bollywood
Models with randomized parameters performed poorly on the Bollywood dataset, with a max test accuracy of 13% and an average of 9%. Transfer learning improved max performance to around 50%, though still below production level. The dataset's low resolution (64x64) and similarity among faces may have contributed to lower performance, indicating that MobileNetV3 may not be ideal for this task.

#### Pokemon
In experiments with the Pokemon dataset, a subset of 6 classes (200 training images) was used. Despite limited training data, the model achieved approximately 97% test accuracy after 10 epochs. MobileNetV3, trained on real-world images, performed well on fictional characters, demonstrating transfer learning's robustness even with minimal data.

---

### Overall Conclusion

Transfer learning is highly effective with limited training data that resembles the model's initial input. However, as the data diverges from the model's original use case or as class similarity increases, transfer learning may face limitations in applicability.
