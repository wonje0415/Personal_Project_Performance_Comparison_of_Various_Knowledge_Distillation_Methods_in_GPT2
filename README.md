# Personal_Project_Performance_Comparison_of_Various_Knowledge_Distillation_Methods_in_GPT2

## Report (written in Notion)

[Report_Comparison_of_Various_Knowledge_Distillation_Methods_in_GPT.pdf](https://github.com/user-attachments/files/23936701/Report_Comparison_of_Various_Knowledge_Distillation_Methods_in_GPT.pdf)

## Goal

- Comparison some combinations of knowledge distillation formulas and Analyzing each combination’s impact to improvement of performance

## Constraint

- GPU : 1 NVIDIA A100
- Storage limitation : 100MB (by using Colab)

## Duration

- 2025.07.08 ~ 2025.09.02 (During Military Services)

## Members

- Wonje Jang (Solo)

## Details

- Student model : customized-TinyGPT, Teacher model : GPT-2 Small
- Combinations of methods : 12.
    - Hidden layers : MSE Loss (layer-wise or last-to-last or last-to-all) : 3
    - output : KL-Divergence or JS-Divergence : 2
    - auxiliary loss to output : cosine similarity loss or not : 2
    - $\therefore \text{The number of combination : } 3 \times 2 \times 2 = 12$
- Two baselines exist
    1. Not using Knowledge Distillation
    2. Using only KL-Divergence to output
- Datasets : WikiText-103
- Perplexity was used as evaluation score.
- Other details are in the report.
    
    

## Results

1. Using only KL-Divergence to output can be efficient solution: it shows similar performance compared to other methods but it has lower computational costs.
    1. Between other methods in hidden layers, there was no large discrepancy in performance.
2. In JS-Divergence, perplexity decreased in early, but it increaseded in last.
    1. It may be beneficial to use in fine-tuning, which has limitations of the number of training epochs
    2. It may be more useful by using as auxiliary loss.
3. Combining cosine similarity loss into the output may help to improve performance.
    1. In JS-Divergence, the impact of cosine similarity loss was noticeable, but in KL-Divergence, it was not.

## What I Learned

1. **Experiment plan** is very important.
    - A well-designed experimental plan can reduce the use of time and money in experiments.
    - Especially, when experiment topic is changed, experiment plan should be changed in same.
    - Codes should follow the experiment plan.
2. **Checking** is crucial in experiments.
    - When we run AI codes, it takes a lot of times. Therefore, several checkings to find flaws of codes such as typing mistake, etc are needed.
    - Being meticulous is crucial for guaranteeing the reliability of experiments.
3. Understanding the meanings of formulas is essential to understand the result and to modify in various ways.
    - Without understanding the meaning of the formulas, the depth of the research inevitably becomes shallow.
    - Understanding mathematical formulas can foster creativity in modifications.
4. Understanding how to implement knowledge distillation
    - Learned how to modify the loss function.
    - Learned how the model architecture should be specifically modified to implement knowledge distillation.
