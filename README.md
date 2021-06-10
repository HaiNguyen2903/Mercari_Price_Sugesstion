# Mercari_Price_Sugesstion
It can be hard to know how much something’s really worth. Small details can mean big differences in pricing.

Product pricing gets even harder at scale, considering just how many products are sold online. Clothing has strong seasonal pricing trends and is heavily influenced by brand names, while electronics have fluctuating prices based on product specs.

[Mercari](https://www.mercari.com), Japan’s biggest community-powered shopping app, knows this problem deeply. They’d like to offer pricing suggestions to sellers, but this is tough because their sellers are enabled to put just about anything, or any bundle of things, on Mercari's marketplace.

In this competition, our challegnge is to build an algorithm that automatically suggests the right product prices. You’ll be provided user-inputted text descriptions of their products, including details like product category name, brand name, and item condition.

# Dataset
In this competition, the objective is to predict the sale price of a listing based on information a user provides for this listing.

The competition includes two stage, where the stage 2's test dataset is much larger (over 3 millions samples) than the test dataset in the first stage (only more than 700k samples)

Since we got struggle while dealing with the huge test dataset from stage 2, we decide to create a new test dataset by splitting 10% from the train dataset. This new test dataset is over 1 million sample, which is larger than the first stage's test dataset while still can be handled. So we decided to use this new test dataset to evaluate our working and experiments.

There are some data versions that are created using diffirent embedding methods. We kept all created and processed data in Drive for easier accessing and usage. This [Drive](https://drive.google.com/drive/u/0/folders/1bRh6xfe6i_Rp6ZnQdMIl1F1T-Z--37k5) contains all data related to our work and all the model's checkpoints for the competition. 

# Experiments 
We tried several models with different data versions to find out the best approach. In summary, here are our experiments's performance:

Mô hình | Preprocessing | Encoded Methods | RMSLE 
--- | --- | --- | ---
Ridge Regression | No | One hot Encoding + TFIDF | 0.5563
Ridge Regression | Yes | One hot Encoding + TFIDF |0.4793
RidgeCV | No | One hot Encoding + TFIDF | 0.4372
RidgeCV | Yes | One hot Encoding + TFIDF | 0.4310
Support Vector Regression | No | One hot Encoding + TFIDF | 0.5111
Support Vector Regression | Yes | One hot Encoding + TFIDF | 0.4715
Stochastic Gradient Regression | Yes | One hot Encoding + TFIDF | 0.4325
Light Gradient Boosting Method | Yes | One hot Encoding + TFIDF | 0.4618
Simple Multi Layer Perceptron | Yes | One hot Encoding + Glove100d | **0.4275**
Convolutional Neural Network | Yes | One hot Encoding + Glove200d | 0.4386


Since the train dataset is splitted 10% to create the new test dataset, so we train only on 90% of the original train dataset. Although the test dataset is not official and not as large as that in the second stage, but I belive that this result is fair enough compare to other team in Stage 1 of the competiton.

So hope you enjoy our work here. :D
