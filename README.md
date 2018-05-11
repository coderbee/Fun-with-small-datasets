
# Fun with small image data-sets
###Baseball or Cricket? US $ or Canadian $?

Suppose you want to build an image classifier for your own specific task. You might think you need a large collection of data. Surprisingly, a small collection of training images are good enough to produce a reasonable accuracy rate (90–100%) accuracy. I’ll discuss two case studies here: classifying the sport in an image as Baseball or Cricket, and identifying a bill image as a US dollar or Canadian dollar.

I’m currently taking the Fastai Deep learning course in San Francisco . It’s been wildly fun so far. The two cases I tried out (Cricket vs Baseball and US dollar vs Canadian dollars) were based on the first lesson. The lesson uses the pre-trained model resnet34 (more details on resnet models by a fellow Fastai student here) as a starting point. Using the fastai framework is pretty easy and fast. Here’s an example of the main piece of the puzzle — calling the learner data object’s fit method to train the model.


The first lesson was a deep dive into using Convolutional Neural Net (CNN) models to get state of the art results on the very popular dogs vs cats Kaggle competition. I’d highly encourage you to check it out here. The lessons are in the form of Jupyter notebooks, you’ll need to have some kind of Deep Learning machine setup (popular choices are AWS, Paperspace instances; or a custom deep learning rig). Crestle is another option that lets you run Jupyter notebooks out-of-the-box with hardly any setup.

##Cricket vs baseball


Cricket and baseball are two sports with similar ‘features’ so I tried to distinguish between them. In order to collect images for training and test, I did a Google Image search for the terms Cricket and Baseball respectively. I downloaded 20 images for each sport and split them into training (15 images) and test(5 images) sets. I was able to get a reasonable accuracy of 90% (9/10 test images correctly classified) with 15 training images. Here are some examples of the images being classified. A prediction score closer to 0 indicates a baseball image.


After playing around with the model I saw that a learning rate of 0.1 gave good results. Since the number of training images is small, I used trial and error to find a good learning rate. The one image incorrectly classified is shown below.


It was possible to get 100% every now and then, by running the model several times and varying hyper-parameters. I’m not sure if 100% accuracy means much though since the number of test images is so low. Going ahead I’d like to try this with a larger number of valid images to see how the model generalizes.

US dollar vs Canadian dollar

I carried out the same experiments using dollar bills this time, using 7 images of US dollars and Canadian dollars each for training, and 5 images for testing respectively. This time the classifier was able to easily achieve 100% accuracy. Here are some example results- a prediction score closer to 0 means the dollar bill is Canadian.


Another common way to analyze the result of a classification model is to use a confusion matrix, which shows the correctly classified categorical variables along the negative 45 diagonal line. In this case, no dollars were misclassified and so we see the [5,0][0,5] pattern below.


##Conclusion

Many fields are plagued with the problem of data collection (bio-medical images, industrial settings). It could be hard or prohibitively expensive to collect enough image data. However, we don’t necessarily need 1000’s of images to build our own custom classifier using a pre-trained model. This is good news for prototyping and doing quick experiments.Here are some further directions worth exploring:

Automate downloading of custom images, so that one can build better and more custom classifiers
Identify techniques/practices that work better for small datasets. Apply them to domains where collecting data is hard/expensive
Try out some fun examples: Ship vs Submarine? Is the human wearing glasses or not?


---------------


# demo-site

## Heading two

### Heading three, etc.

Any text with no empty lines between will become a paragraph.
Font can be *Italic* or **Bold**.
Code can be highlighted with `backticks`.

Links look like this [GitHub Help](https://help.github.com/).

List:
- dog
- cat

Numbered:
1. one
2. two 

> Block quote.

----
