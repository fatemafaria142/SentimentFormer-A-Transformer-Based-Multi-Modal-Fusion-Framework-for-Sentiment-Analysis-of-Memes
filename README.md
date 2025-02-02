# SentimentFormer: A Transformer-Based Multi-Modal Fusion Framework for Enhanced Sentiment Analysis of Memes in Under-Resourced Bangla Language
## Abstract
Social media has increasingly relied on memes as a tool for expressing opinions, making meme sentiment analysis an emerging area of interest for researchers. While much of the research has focused on English-language memes, under-Resource languages, such as Bengali, have received limited attention. Given the surge in social media use, the need for sentiment analysis of memes in these languages has become critical. One of the primary challenges in this field is the lack of benchmark datasets, particularly in languages with fewer resources. To address this, we used the MemoSen dataset, designed for Bengali, which consists of 4,368 memes annotated with three sentiment labels: positive, negative, and neutral. MemoSen is divided into training (70%), test (20%), and validation (10%) sets, with an imbalanced class distribution: 1,349 memes in the positive class, 2,728 in the negative class, and 291 in the neutral class. Our approach leverages advanced deep learning techniques for multimodal sentiment analysis in Bengali, introducing three hybrid approaches. SentimentTextFormer is a text-based, fine-tuned model that utilizes state-of-the-art transformer architectures to accurately extract sentiment-related insights from Bengali text, capturing nuanced linguistic features. SentimentImageFormer is an image-based model that employs cutting-edge transformer-based techniques for precise sentiment classification through visual data. Lastly, SentimentFormer is a hybrid model that seamlessly integrates both text and image modalities using fusion strategies. Early Fusion combines textual and visual features at the input level, enabling the model to jointly learn from both modalities. Late Fusion merges the outputs of separate text and image models, preserving their individual strengths for the final prediction. Intermediate Fusion integrates textual and visual features at intermediate layers, refining their interactions during processing. These fusion strategies combine the strengths of both textual and visual data, enhancing sentiment analysis by exploiting complementary information from multiple sources. The performance of our models was evaluated using various accuracy metrics, with SentimentTextFormer achieving 73.31% accuracy and SentimentImageFormer attaining 64.72%. The hybrid model, SentimentFormer (SwiftFormer with mBERT), employing Intermediate Fusion, shows a notable improvement in accuracy, achieving 79.04%, outperforming SentimentTextFormer by 5.73% and SentimentImageFormer by 14.32%. Among the fusion strategies, SentimentFormer (SwiftFormer with mBERT) achieved the highest accuracy of 79.04%, highlighting the effectiveness of our fusion technique and the reliability of our multimodal framework in improving sentiment analysis accuracy across diverse modalities.

## Table of Contents
- [Proposed Methodology](#experimental-methodology)
- [Dataset Availability](#dataset-availability)
- [Results](#results)
- [Citation](#citation)
- [Contact Information](#contact-information)

## Proposed Methodology
![Methodology](Retina_Fundus.jpeg)

    
## MemoSen Dataset for Bengali Multimodal Sentiment Analysis  

In this study, we leverage the [MemoSen](https://github.com/eftekhar-hossain/MemoSen-LREC2022) dataset, a multimodal resource specifically curated for sentiment analysis in the Bengali language, to conduct our experiments. MemoSen was meticulously developed to address the lack of resources for multimodal sentiment analysis in Bengali. The dataset comprises **4,368 memes** collected from **Facebook, Twitter, and Instagram** between **February 2021 and September 2021**, using keywords such as **"Bengali Memes," "Bengali Funny Memes,"** and **"Bengali Troll Memes"** to ensure a diverse representation. The dataset includes memes with captions in **Bengali, code-mixed (Bengali and English), or Banglish (code-switched)**. During curation, memes lacking visual or textual components, containing unreadable text, or being duplicates were removed. The final dataset is annotated into three sentiment categories: **Positive, Negative, and Neutral**, following strict guidelines to ensure consistency and reduce annotation bias. For training and evaluation, the dataset is split into **train (70%), test (20%), and validation (10%)** subsets.

## Results
### Performance Evaluation of Pretrained CNNs for Fundus Image Classification

| Model             | Accuracy | Precision | Recall  | F1 Score | Jaccard Score | Log Loss |
|-------------------|----------|-----------|---------|----------|---------------|----------|
| ResNet101         | 0.9417   | 0.9435    | 0.9417  | 0.9418   | 0.8902        | 0.2254   |
| DenseNet169       | 0.9333   | 0.9378    | 0.9333  | 0.9333   | 0.8751        | 0.9080   |
| Xception          | 0.9250   | 0.9284    | 0.9250  | 0.9252   | 0.8612        | 1.3931   |
| InceptionV3       | 0.9167   | 0.9203    | 0.9167  | 0.9166   | 0.8480        | 0.8012   |
| DenseNet121       | 0.9083   | 0.9092    | 0.9083  | 0.9075   | 0.8320        | 4.5509   |
| InceptionResNetV2 | 0.9000   | 0.9049    | 0.9000  | 0.9008   | 0.8202        | 12.0282  |
| ResNet50          | 0.8917   | 0.8948    | 0.8917  | 0.8926   | 0.8089        | 0.4883   |
| EfficientNetB0    | 0.8833   | 0.8862    | 0.8833  | 0.8837   | 0.7947        | 0.6697   |



### U-Net Variants Performance Assessment for Retinal Blood Vessel Segmentation

#### Using the DRIVE Dataset 

| Models          | Backbone           | Intersection over Union (IoU) | Dice Coefficient | Mean Pixel Accuracy | Mean Modified Hausdorff Distance | Mean Surface Dice Overlap |
|-----------------|--------------------|--------------------------------|------------------|---------------------|----------------------------------|---------------------------|
| TransUNET       | ResNet50V2         | 0.5273                         | 0.6899           | 0.6470              | 3.852                            | 0.0151                    |
|                 | ResNet101V2        | 0.5169                         | 0.6803           | 0.6400              | 4.0864                           | 0.0188                    |
|                 | ResNet152V2        | 0.5250                         | 0.6879           | 0.6514              | 4.052                            | 0.0167                    |
| Attention U-Net | ResNet50V2         | 0.6460                         | 0.7848           | 0.7953              | 2.7150                           | 0.0070                    |
|                 | ResNet101V2        | 0.6483                         | 0.7865           | 0.8023              | 2.7341                           | 0.0054                    |
|                 | ResNet152V2        | 0.6474                         | 0.7859           | 0.7859              | 2.6718                           | 0.0069                    |
|                 | DenseNet121        | 0.6427                         | 0.7824           | 0.7747              | 2.7484                           | 0.0090                    |
|                 | DenseNet169        | 0.6444                         | 0.7837           | 0.7769              | 2.6776                           | 0.0072                    |
|                 | DenseNet201        | 0.6422                         | 0.7827           | 0.7749              | 2.6475                           | 0.0074                    |
| Swin-UNET       | Swin Transformer   | 0.4896                         | 0.6569           | 0.6062              | 4.3675                           | 0.0178                    |

#### Using the FIVES Dataset 

| Models          | Backbone           | Intersection over Union (IoU) | Dice Coefficient | Mean Pixel Accuracy | Mean Modified Hausdorff Distance | Mean Surface Dice Overlap |
|-----------------|--------------------|--------------------------------|------------------|---------------------|----------------------------------|---------------------------|
| TransUNET       | ResNet50V2         | 0.6436                         | 0.7791           | 0.7758              | 3.7392                           | 0.0312                    |
|                 | ResNet101V2        | 0.6559                         | 0.7898           | 0.7764              | 3.5491                           | 0.0285                    |
|                 | ResNet152V2        | 0.6522                         | 0.7866           | 0.7696              | 3.5278                           | 0.0319                    |
| Attention U-Net | ResNet50V2         | 0.7175                         | 0.8353           | 0.8512              | 2.8913                           | 0.0201                    |
|                 | ResNet101V2        | 0.7221                         | 0.8385           | 0.8507              | 2.8009                           | 0.0223                    |
|                 | ResNet152V2        | 0.7199                         | 0.8369           | 0.8331              | 2.8134                           | 0.0378                    |
|                 | DenseNet121        | 0.6872                         | 0.8143           | 0.7866              | 3.2814                           | 0.0591                    |
|                 | DenseNet169        | 0.6718                         | 0.8024           | 0.8115              | 3.5513                           | 0.0235                    |
|                 | DenseNet201        | 0.6468                         | 0.7822           | 0.7587              | 3.6267                           | 0.0293                    |
| Swin-UNET       | Swin Transformer   | 0.5179                         | 0.6765           | 0.5987              | 4.6090                           | 0.0891                    |

### Comparative Analysis of Explainable AI Methods
![Results](Retina_Fundus_XAI.jpeg)


## Contact Information

For any questions, collaboration opportunities, or further inquiries, please feel free to reach out:

- **Fatema Tuj Johora Faria**
  - Email: [fatema.faria142@gmail.com](mailto:fatema.faria142@gmail.com)

- **Mukaffi Bin Moin**
  - Email: [mukaffi28@gmail.com](mailto:mukaffi28@gmail.com)

- **Pronay Debnath**
  - Email: [pronaydebnath99@gmail.com](mailto:pronaydebnath99@gmail.com)
- **Asif Iftekher Fahim**
  - Email: [fahimthescientist@gmail.com](mailto:fahimthescientist@gmail.com)
    
## Citation

If you find the dataset or the associated research work helpful, please consider citing our paper:

```bibtex
@misc{faria2023vashantor,
  title={Vashantor: A Large-scale Multilingual Benchmark Dataset for Automated Translation of Bangla Regional Dialects to Bangla Language},
  author={Fatema Tuj Johora Faria and Mukaffi Bin Moin and Ahmed Al Wase and Mehidi Ahmmed and Md. Rabius Sani and Tashreef Muhammad},
  year={2023},
  eprint={2311.11142},
  archivePrefix={arXiv},
  primaryClass={cs.CL}
}

