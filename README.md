# HazardousWeatherAlert-JetsonAI

## About: 
An AI program made on the Nvidia Jetson Nano that is designed  to find hostile weather that could damage solar panels and make decisions on weather or not :p, pun intended! , to close a lid that would protect the equipment. This AI was trained using the resnet 18 AI image training model. The datasets used came from Kaggle.com (https://www.kaggle.com/datasets/jehanbhathena/weather-dataset) and contained 6862 images of weather. The model was trained on 5 (Fog/Smog, Frost, Hail, Lightning, Sandstorm)of these types of weather that could be deemed harmful to solar panel equipment.

![image of jetson nano](https://github.com/ScratchyCat-MIT/HazardousWeatherAlert-JetsonAI/assets/59852805/0490009b-145d-44a7-8a31-00ce09bbe4ed)

*Picture of Jetson Nano developer kit, these are basically mini computers that come built in with a small graphics card that is good for image processing, a Jetson Nano can be found regularly for $150 or less: https://developer.nvidia.com/buy-jetson?product=jetson_nano&location=US*

![image of a sandtorm](https://github.com/ScratchyCat-MIT/HazardousWeatherAlert-JetsonAI/assets/59852805/d9498a6b-08a3-4e12-beb7-02c750c63287)

# Instructions for use:

>***This project was made for the Jetson Nano's specific hardware, you may try using other operating systems, but the steps will be diffrent and you will need to do your own research. With all that said, good luck!***
---
>***P.S Mac Users, you can most likely follow along with most of this by using some sort of graphics card and installing hombrew (A command line package manager) [here](https://brew.sh/) or here: https://brew.sh/***
![image of mac user](https://github.com/ScratchyCat-MIT/HazardousWeatherAlert-JetsonAI/assets/59852805/502de82a-211a-40d4-8b34-ec01dba8d516)
---
>***Also another P.S windows users you can completely follow along by downloading a virtual machine or downloading windows subsystem for linux which gives users a linux terminal in their windows install. For info on that click [here](https://learn.microsoft.com/en-us/windows/wsl/install) or here: https://learn.microsoft.com/en-us/windows/wsl/install***

---

![image of windows user](https://github.com/ScratchyCat-MIT/HazardousWeatherAlert-JetsonAI/assets/59852805/bd4ad394-65b7-4d00-b6dd-fe83f5b17b48)


## Download the files necessary for the project.

Before any installing happens make sure that you have python installed.

For first iteration: (Less Accurate) `wget https://www.dropbox.com/s/2s1mku43hvyr9n6/classificationFirstIteration.zip`
For second iteration: (More Accurate) `wget https://www.dropbox.com/s/vywzeue5is5rkbr/classificationSecondIteration.zip`

This command accesses a dropbox zip file that has all the necessary files for the project, if you would like the first iteration of the project than there is a link in it's folder.

Next we have to unzip the file, there are many different ways to unzip a zip file, including directly in the linux desktop, but you can also install a program called unzip, unzip will unzip zip files and you can install this using these commands.

`sudo apt-get update` and `sudo apt-get install unzip`

Now that unzip is installed we can use it to unzip the file using this command.

`unzip classificationFirstIteration.zip` or
`unzip classificationSecondIteration.zip`

After the file is done unziping you will need to find and run the model, this may take a few minutes as the model initializes and learns, you cn run the model using this command.

First CD into the directory of the model with

`cd classification`

Then set the DATASET and NET variables that determine the path of your model, after 

`DATASET=data/weather`
`NET=models/weather`
`imagenet.py --model=$NET/resnet18.onnx --input_blob=input_0 --output_blob=output_0 --labels=$DATASET/labels.txt $DATASET/test/weather/4667.jpg weatherOutputTest.jpg`

Now your AI model should work! Have fun testing different images. Look below for different images that you can test, and here is a link for other ways you can use this model [here](https://github.com/dusty-nv/jetson-inference/blob/master/docs/pytorch-cat-dog.md#processing-all-the-test-images) or here: https://github.com/dusty-nv/jetson-inference/blob/master/docs/pytorch-cat-dog.md#processing-all-the-test-images.

![image](https://github.com/ScratchyCat-MIT/HazardousWeatherAlert-JetsonAI/assets/59852805/216eaa94-6d5d-4ccd-b8df-4c1f33676748)


# Examples of AI predicting weather (1st Iteration, 150 epochs (An epoch is basically one iteration of the AI)):
![Fog Smog](https://github.com/ScratchyCat-MIT/HazardousWeatherAlert-JetsonAI/assets/59852805/856dd814-1770-4e9b-a17a-1f81e5139a61)
![Fog Smog](https://github.com/ScratchyCat-MIT/HazardousWeatherAlert-JetsonAI/assets/59852805/2b09f134-ccec-4eb9-9ca7-b9e14d102084)
![Fog Smog](https://github.com/ScratchyCat-MIT/HazardousWeatherAlert-JetsonAI/assets/59852805/8a6026f8-4449-4194-9f3f-231b4d5e217c)

## 

![9](https://github.com/ScratchyCat-MIT/HazardousWeatherAlert-JetsonAI/assets/59852805/2a7a0107-e42e-40d9-abd1-b3e1d1ae7ac1)
![8](https://github.com/ScratchyCat-MIT/HazardousWeatherAlert-JetsonAI/assets/59852805/b90960b3-3b32-4f10-95be-a2dabd4ee876)

##

![7](https://github.com/ScratchyCat-MIT/HazardousWeatherAlert-JetsonAI/assets/59852805/13774f47-499a-4711-bc45-0be69e498c45)
![6](https://github.com/ScratchyCat-MIT/HazardousWeatherAlert-JetsonAI/assets/59852805/afc64610-bdd1-4e59-86c4-1cd146539aac)
# Examples of AI predicting weatehr (2nd Iteration, 300 epochs):
