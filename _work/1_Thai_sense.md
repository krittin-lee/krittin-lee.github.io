---
layout: work
title: "THAI-Sense"
description: "An NLP project that builds transformer-based models to identify jokes and controversial humor in thai text."
image: "https://placehold.co/1000x600/9cd2aa/white?text=THAI-Sense"
year: "2024"
role: 
emoji: "🗣️"
month_season: April - May
for: "Natural Language Processing Systems III course"
team: "Kuntida Kongkad, Chidapha Phongkhahabodi"
advisors: "Attapol Rutherford"
tool: Python, pre-trained LLM models,
order: "1"
---

#### Acess [the paper here ⎘](https://krittin-lee.github.io/ETC/SemEval-2021%20Task%207.pdf)

This project was developed as part of **SemEval-2021 Task 7: HaHackathon**, focusing on automatic detection and interpretation of humor and offensive content in short texts. The goal was to understand how modern NLP systems handle highly subjective language phenomena such as jokes, sarcasm, and controversial humor.

## Project Overview

The system addresses three related NLP tasks:

- **Humor detection**: predicting whether a text is intended to be humorous  
- **Humor rating**: estimating how funny a humorous text is on a continuous scale  
- **Controversy detection**: identifying whether a joke is likely to be perceived as controversial  

To solve these tasks, We experimented with multiple transformer-based models, including **RoBERTa**, **BERT**, **XLNet**, and **ALBERT**, and compared their performance against traditional machine learning baselines.

## Approach

The project primarily relied on fine-tuning pre-trained transformer models for both classification and regression tasks. Humor detection and controversy detection were treated as binary classification problems, while humor rating was framed as a regression task. This distinction proved important: treating humor ratings as a continuous value significantly improved performance compared to discretized classification approaches.

We also explored model selection, hyperparameter tuning, and baseline comparisons, which helped clarify when large pre-trained models provide meaningful gains over simpler methods.

## Results and Insights

RoBERTa-base achieved strong results in humor detection, demonstrating how well transformer models capture linguistic patterns associated with jokes. For humor rating, BERT-based regression models performed best, reinforcing the importance of aligning model design with the nature of the target variable. Controversy detection remained the most challenging task due to label imbalance and the subtle, culturally dependent nature of offensive humor.

Error analysis revealed that models often struggle with sarcasm, irony, and implicit social references—highlighting the limits of surface-level language understanding.

## What I Learned

Through this project, I gained hands-on experience with:

- Fine-tuning transformer models for **classification and regression**
- Evaluating NLP systems using task-appropriate metrics (F1-score, RMSE)
- Understanding dataset bias, label imbalance, and subjective annotations
- Performing qualitative error analysis to uncover model weaknesses
- Appreciating the complexity of modeling social and cultural meaning in language

Overall, this project deepened my understanding of applied NLP and reinforced the idea that strong quantitative performance does not always imply true semantic or cultural understanding—especially in tasks involving humor and offense.

---------------------------------<br>

#### Acess [the paper here ⎘](https://krittin-lee.github.io/ETC/SemEval-2021%20Task%207.pdf