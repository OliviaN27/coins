# Project Name
Hi! I decided to make my NVIDIA Project with the Jetson Nano able to identify diferent kinds of coins from diferent currencies. The purpose of this project is to help people traveling internationally know which coins they need and what they look like.

https://imgur.com/eFipMd6

## The Algorithm

Add an explanation of the algorithm and how it works. Make sure to include details about how the code works, what it depends on, and any other relevant info. Add images or other descriptions for your project here. 

## Running this project

1. First make sure you have installed VS Code, Putty, or Terminal
2. Make sure you are in this classification directory: jetson-inference/python/training/classification/
3. Find or make a dataset. To find one you can use a website like Kaggle. Here is the one that I used: https://www.kaggle.com/datasets/wanderdust/coin-images
4. Go back to the jetson-inference folder and run this: ./docker/run.sh
5. After go back to this directory: jetson-inference/python/training/classification/
6. Now you need to train the nano. To do that you can use this command (change the word coins to the name of your dataset): python3 train.py --model-dir=models/coins data/coins
7. After you are done training you can test it out. You can use these commands:
   $ NET=models/coins
   $ DATASET=data/coins
8. Then run this command and choose which image you want to test: imagenet.py --model=$NET/resnet18.onnx --input_blob=input_0 --output_blob=output_0 --labels=$DATASET/labels.txt $DATASET/test/5/009__20 Cents_australia.jpg 5.jpg

Here is my demonstration video:
