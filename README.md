# Research

Research papers and reports by [Bilal Munawar](https://github.com/bm2515) from NYU and NYU Shanghai, covering NLP, computer vision, and big-data analytics.

| Paper | Area | Year |
| --- | --- | --- |
| [Urdu Extractive Summarization](#1-urdu-extractive-summarization) | NLP · Transformers | 2021 |
| [A Multi-Task Learning Approach to Top-Down Ego-Car View Generation](#2-a-multi-task-learning-approach-to-top-down-ego-car-view-generation) | Computer vision · Self-driving | 2020 |
| [Big-Data-Driven Car Speeding Prediction for NYC](#3-big-data-driven-car-speeding-prediction-for-nyc) | Big data · Urban analytics | 2019 |

---

## 1. Urdu Extractive Summarization
**Abubakar Zahid, Bilal Munawar**, supervised by Wilson Tam · NYU Shanghai Computer Science Capstone, Spring 2021
📄 [Read the paper (PDF)](papers/urdu-extractive-summarization.pdf)

Urdu is spoken by over 250 million people but has very few NLP resources. This is the **first deep-learning approach to text summarization in Urdu**.
- Built **RoBERTaSUM**, which fine-tunes RoBERTa-urdu together with summarization layers (a classifier, an inter-sentence Transformer, and an LSTM). We also built an unsupervised method using RoBERTa embeddings and K-Means clustering.
- Created a new labeled dataset of **100 Urdu news articles** from the Makhzan corpus. Combined with the existing UCE dataset, that gives 150 articles for training.
- RoBERTaSUM + Transformer reached **42.70 ROUGE-L**, beating the previous best method (38.10).

**Stack:** PyTorch, Hugging Face Transformers, Urduhack

---

## 2. A Multi-Task Learning Approach to Top-Down Ego-Car View Generation
**William Huang, Haoyue Ping, Bilal Munawar** · NYU Deep Learning (Spring 2020), final project
📄 [Read the paper (PDF)](papers/multitask-top-down-ego-car-view.pdf) · 💻 [Code](https://github.com/wh629/deep_learning_project)

Generates a top-down map around a self-driving car from its 6 surround-view camera images, detecting nearby objects and predicting the road layout at the same time.
- Built an encoder-decoder model with a shared **ResNet50** encoder and two decoders: a **Faster R-CNN** head for bounding boxes and a deconvolutional head for an 800×800 binary road map.
- Pre-trained the encoder with a self-supervised **Jigsaw** task on unlabeled data to make up for the small labeled set.
- Includes a candid post-mortem of what went wrong (exploding gradients during pre-training, road-map predictions collapsing to the mean, and the two tasks interfering with each other) and what we would change.

**Stack:** PyTorch, ResNet50, Faster R-CNN, NYU Prince HPC cluster

---

## 3. Big-Data-Driven Car Speeding Prediction for NYC
**Yeqian Yang, Roni Yosofov, Bilal Munawar** · NYU Realtime and Big Data Analytics, Fall 2019
📄 [Read the paper (PDF)](papers/nyc-car-speeding-prediction.pdf)

Finds where, when and in what conditions NYC drivers are most likely to speed, to help police decide where to place patrol cars under the city's Vision Zero program.
- Joined **25M+ rows (12 GB)** of NYC DOT real-time traffic-speed data with hourly Central Park weather and the city's speed-limit map. Records were matched by timestamp and GPS coordinates using **Hadoop MapReduce** and **Hive**.
- Found that speeding concentrates on a few specific roads in the Bronx, Queens and Brooklyn, mostly between 8 pm and 7 am, and in clear, calm or very cold weather.
- Turned the results into concrete patrol recommendations.

**Stack:** Hadoop MapReduce, Hive, Impala, HDFS, NYU HPC
