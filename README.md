# Emotional-Analysis-in-Chinese-Social-Media
Fine-Tuning LLMs to Analyze Emotions in Social Media Comments

## Introduction
The results of the emotional analysis presented here are used in my research, titled "Investigating the Effect of Public Negativity on Member Engagement in Online Fan Community ". This analysis is conducted using the Chinese-RoBERTa model. For clarity and to assist beginners, I have provided detailed, line-by-line interpretations in the code to make the concepts more accessible. This method illustrates how Large Language Models (LLMs) can be effectively integrated with econometric techniques, offering potential benefits for your own research or study.

## Dataset
### Training and Testing Dataset
Ren-CECps Chinese dataset (Quan and Ren, 2010): This dataset includes 35,096 sentences extracted from various blogs, annotated with eight emotion labels: anger, expectation, anxiety, joy, love, hate, sorrow, and surprise. Access to the dataset can be obtained by directly contacting the authors of Quan and Ren (2010).
### Research Dataset (Data Apply the Trained Model)
Social Media Data from China: This dataset was compiled by crawling data from three online fan communities in China. It includes 4,752 original posts along with 107,414 comments, providing a rich source of user-generated content for analysis. Sample data is available upon request.

## Fine-Tuning Objective:
Adapt a pre-trained model, i.e., Chinese-RoBERTa (https://huggingface.co/hfl/chinese-roberta-wwm-ext), which has been trained on a large, general dataset. By fine-tuning this model to a specialized social media dataset related to my research, it demonstrates enhanced classification performance for analyzing social media comments.
## Model Architecture
This configuration describes a BertForMultilabelSequenceClassification model, specifically the hfl/chinese-roberta-wwm-ext version, designed for multilabel sequence classification tasks. Specifically, it

- features 12 hidden layers with 768 hidden units each, and 12 attention heads.
- uses GELU activation function for bidirectional processing.
- with a vocabulary size of 21,128, supports sequences up to 512 tokens in length.
- attention and hidden dropout probabilities are set at 0.1, ensuring regularization during training.
- mapping for up to nine labels: 'anger','anxiety','expect','hate','joy','love','sorrow','surprise','neutral'.
  
## Usage
To train and evaluate the model: Tune_Emotional_Model.ipynb
To apply the model on social media comments data: Apply_TunedModel_Comments.ipynb
## Dependencies
The code was executed on Google Colab using a GPU with Persistent-RAM.
## License
Code available under MIT license.

## References
Cui, Y., Che, W., Liu, T., Qin, B., and Yang, Z. 2021. "Pre-Training with Whole Word Masking for Chinese Bert," IEEE/ACM Transactions on Audio, Speech, and Language Processing (29), pp. 3504-3514.
Li, Y., and Fei, L. 2021. "Applying Language Model in Business Research," in: Workshop at Hong Kong Polytechnic University.
Quan, C., and Ren, F. 2010. "A Blog Emotion Corpus for Emotional Expression Analysis in Chinese," Computer Speech & Language (24:4), pp. 726-749.
