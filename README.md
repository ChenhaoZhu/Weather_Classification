# Weather_Classification

# Our data is found on kaggle, and here is the kaggle dataset link : https://www.kaggle.com/datasets/vijaygiitk/multiclass-weather-dataset
# Also, we upload the kaggle dataset into our drive and here is the shared drive link : https://drive.google.com/drive/folders/1vBxCKRGNq8gs9xU6i3F4AjWyZzAuMQmn?usp=sharing



Our group intends to classify weather images first, and then convert severe weather images into clear images that are easier to identify. Our project has a wide range of application scenarios like autonomous driving. Specifically, Severe weather phenomena have various negative effects on transportation. As a source of information for vehicle sensors, the state of the environment is directly influenced by weather conditions. For camera-led multi-sensor fusion system which is one of the mainstream, it is particularly important to recognize the weather through images and obtain surrounding information based on clear pictures.

For the classification part, we tried three different networks and chose the one that performed the best which is resnet101. Firstly, we dowanload data from kaggle and divide labeled data into 5 classes which is Sunrise, Shine, Rainy, Foggy, Cloudy. This is what the raw data looks like. We split the data into training set and validation set in a ratio of 2:1 and Resize image into 255:255. For training and validation set, the input is pictures and the output is the probability that the image belongs to each class.

For practicality, we use videos recorded by in-car cameras downloaded from youtube as our test data. We use the code to capture a picture of the video every 30s, and output the probability of belonging to each weather based on the screenshot.

For the defrog and derain part, unfortunately, this part is quite challenging for us, we used cycle gan but did not get good results.
The purpose of image translation is to map the input from the source domain to the target domain. Similar tasks include image coloring, domain adaptation, data augmentation and so on. Transferring weather conditions is important for photographic style transfer. Although lots of approaches have been proposed in traditional image translation tasks, few of them can handle the multi-category weather translation task, since weather conditions have rich categories and highly complex semantic structures.

Our project has a wide range of application scenarios. For example, we can classified the weather automatically and process bad weather pictures obtained by driving recorders to allow drivers to make better judgments. In view of the fact that the driving recorder is often installed behind the front windshield, using the wiper can ensure that the clarity of the picture will not be affected by the raindrops on the glass. Also, reversing cameras often get very blurry images due to bad weather. It can also help drivers get a better view based on similar ideas

# Classification Analysis

# For one try of testing, we used yoturb video depend on each weather condition. Because we are using our model to real-world, we need to see how our model perform on the real-world weather classification at driving.
The shared link on drive about five yoturb video is below : https://drive.google.com/drive/folders/10E1oLFdjpivQNiQnFSVpzDtjwNuo5Yu9?usp=sharing

Our testing result on real-driving video shows that resnet101 is the best model among our three models. However, the accuracy is still worth of improving. There are several points that our model need to improve.
Because we are supposed to train a model on recoginizing weather condition while driving, we could add some data from driving car carmera. Our training model do not include many pictures on that. The reason why we do not include any images into the training could be stated in two main points. First, the car camera video is hard to find, either searching on yoturb or recording by ourselves is time-consuming and difficult. Secondly, we want to see the performance of just trainig model with regular weather images. As shown until, the best performance on test data set is around 85 % . We can say this result is relatively good because of our limit on training data. If we add some picture while driving into the training part, we could possibly get a higher test accuracy on real-world.

# Image Stype Transfer
Our next step is going toward "how we could make use of our correctly identitied weather". What is the use of "weather classification" ? Once we recognize the current weather, like raniy or foggy. Could we make the image more clear ? One possible discussion among our group is to think about using SVD, dimension reduction, to get rid of the background. However, it does not help because drivers still need to watch the road even thought he current weather is rainy or foggy. Then we search for the method to clear the fog and rain so that we could let the driver see more clear about what is going on.
