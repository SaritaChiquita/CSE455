## CSE 455 Final Project
by Sarah Scott

[Final Project Video Presentation](https://youtu.be/s8ON1AoQHXo) 

[Source Code](https://colab.research.google.com/drive/1EYdY-NgAJ3EEGwqK7FYY7n5zkrVKLwn5?usp=sharing)

### Kaggle Bird Classifier - Problem Description
```markdown
My original problem was to create a cat and dog classifier. After I began,
it seemed like too easy of a problem to solve compared to the
very large bird dataset that professor Redmon posted to Kaggle. 
I changed my project to be a bird classifier and classify 555 types of 
birds instead of classifying only between cats and dogs
```
### Previous work (including what you used for your method i.e. pretrained models)
- I gathered lots of inspiration from the Pytorch tutorials that were posted on Tuesdays. When I started creating my classifier, I wanted to create something solely from scratch and after running my CNN and seeing the extremely low accuracy rate for both training and testing, I decided to follow advice that I received during office hours and build my project off of the tutorial base. 
- I also wanted to use a pretrained model to help with my accuracy issue. When I first began, my testing accuracy was less than 1%, which given my small initial testing dataset, was less than randomly choosing one of the twelve bird names I was testing
- I started with using EfficientNet because it is a pyvision pretrained model that utilizes BirdSnap and I thought that it might help me acheive a higher accuracy... But it did not. I spent days training and altering different aspects of the model on a subset of the Birds! data set and got very good training and testing accuracy. When I began to use the entire dataset, everything changed and my accuracy for both was very low.
- Next, I experimented with ResNet 50, a 50 layer artificial neural network and after experiementing with different data augmentations, learning rates, and number of epochs, I was able to increase my training and testing accuracy.

### Your approach
```markdown
- My approach since the dataset of birds is massive, was to start by 
creating a smaller dataset with only two birds and ten training images 
of each bird while I got my training function up and running. After 
this dataset was able to be interpreted correctly, I created a larger
dataset with twelve different birds as well as a testing set that only
contained images of these twelve birds. Since this is a much larger 
dataset, I became more focused on increasing my learning and testing
rate. The odd thing is that when I transferred my Kaggle notebook to
Google Colab, my training accuracy plummeted. It was around 99% when
using Kaggle and then went down to 33% on Google Colab. 

- To increase the accuracy, I decided to use transfer learning and import 
a pretrained model. I initially thought that the best model for this task
was EfficientNet and I started experimenting with different batch 
sizes, number of epochs, and the size of the testing and training 
images to find the most accurate combination. Unfortunately, when I 
used this model with the entire dataset, my accuracy crashed. 

- This is when I began to use ResNet50 and both accuracies increased. 
I then began to rework and include many of the data augmentations 
that were listed in lecture (horizontal flips, color jitter, ect.) 
and my training accuracy increased to 99%
```
### Datasets
I used the Birds! Dataset on Kaggle with a few folder name 
modifications because Google Colab indexes folders differently 
than a numerical ordering. I also created an updated names file
which matched each bird name to the index of the training data folder.

### Results
```markdown
My final results ended up being 99% training accuracy 
and 32.8% testing accuracy
```

### Discussion
What problems did you encounter?
  
- It took me quite a bit of time to get Google Colab’s Jupyter notebook working since I was not familiar with pytorch other than the in-class tutorial. For the first week, I ended up transferring my data to Kaggle’s notebook feature because I kept getting strange checkpoint errors on Colab. After an embarrassingly long time in office hours, we were able to get Google Colab finally working and I was able to transfer my Kaggle notebook.
- I also encountered issues with long training and testing times which made experimenting with different learning rates and number of epochs very time consuming.    Furthermore, the more training images I had, the lower my training rate became, so I switch my pretrained model to EfficientNet and then ResNet50 after finding it on Torchvision’s model API
Are there next steps you would take if you kept working on the project?
-I can definitely make this classifier better with more time. I have a definitive overfitting problem and I believe that I can fix this issue with adding more data      augmentation and cross-validation.
How does your approach differ from others? Was that beneficial?
-I am not sure if my approach differed from others, but I did get a lot of help during office hours to help me decide to start with a pretrained model. This helped me quite a bit because on my “from scratch” model, both accuracies were abysmal. 

