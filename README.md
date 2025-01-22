# CAIS++ Fall 2024 Winter Curriculum Project

Leyaa George | leyaageo@usc.edu

*NOTE: If you are attempting to see the code, click the file that says "CLICKTHISONE" at the end. 

## Project Description
This is a classifier model, built on BERT, that uses natural language processing to detect whether an article is sarcastic or not based on its headline.

## Project Implementation

*Dataset:* I used the "News Headlines Dataset For Sarcasm Detection" by Rishabh Misra on Kaggle. To preprocess the data, I forst split the data by the headlines and the labels (sarcastic or not), discarding the article links because they had no impact on the classification. Then I tokenized the data, before splitting it into a test and train set. 

*Model Development and Training:* For the training, I put the data through the pretrained BERT For Sequence Classification. I chose a batch size of 16 because of the lower memory usage and potentially better generalization, and the AdamW optimizer because of its better performance with large models like BERT. Within AdamW I did a learning rate of 2e-5 and epsilon of 1e-8 because it is small enough to not overwrite BERT's pretraining. I chose 4 epochs so the model could learn more complex patterns, but not crash my computer or hit the GPU usage limits. 

*Model Evaluation/Results:* By the 4th epoch my model had a 94% accuracy, and its MCC Score 0.969. 

## Project Reflection

My model does relatively well, with a 94% accuracy and 0.969 MCC. For something like sarcasm detection, which can be extremely difficult in text with not verbal tonage even for real humans to detect, that is pretty good. 

The implications of being able to detect sarcasm in text could be extended to benefit the public, particularly neurodivergent individuals, who often have a harder time detcting sarcasm. The model could aid these individuals in detecting which textual statements are sarcastic and which ones are those, and perhaps gradually these individuals themselves could even learn like the model. We could develop an app that makes a game out of such detection for young autistic children, for example, to teach them what sarcasm looks like and how to detect it, using this model as the foundations for such detection. Or perhaps the user could feed in a sentence, like a text they got or a sentence they were reading, and the app could tell them whether it is sarcastic or not. 

If I were the continue this project I would expirement further with the hyperparameters to increase the accuracy even further. I would also start introducing more data, such as text messages or tweets, or even augment my own data based on pre-existing datasets so that the model has more data to train on. This would generalize the model so it could work outside just news headlines and make it potentially applicable and useful for the larger public. 

## Source Drawn On
Lesson 4 NLP: Fine-Tune BERT notebook by CAIS++ (https://colab.research.google.com/drive/1NrVDXktmixZuHIILBUujVp9nCwwGsPu8?usp=sharing)

News Headlines Dataset For Sarcasm Detection by Rishabh Misra (https://www.kaggle.com/datasets/rmisra/news-headlines-dataset-for-sarcasm-detection?select=Sarcasm_Headlines_Dataset.json)
