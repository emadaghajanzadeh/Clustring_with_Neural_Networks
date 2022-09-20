# Clustring_with_Neural_Networks


## Discription

In this project, I tried to simulate well-known algorithm of [K-means](https://medium.com/data-folks-indonesia/step-by-step-to-understanding-k-means-clustering-and-implementation-with-sklearn-b55803f519d6) with popular deep learning models in order to perform clustering on a bunch of data, specifically, MNIST. Below I firstly touch on what the K-means algorithm does in my own language and then I show how a deep neural network (DNN) model can do the same in a creative way. It is also worth mentioning that here the main purpose is not to increase performance compared to K-means (although any improvements were welcomed) but to illustrate insightful training algorithms using deep learning models.

## K-means

K-means always started with initializing important parameters of K and initial cluster centers which is also important, and bad initialization of them can result in bad performance. Readers are referred to [this straightforward experiments](https://medium.com/geekculture/why-do-initial-cluster-centroids-in-k-means-affect-the-final-cluster-generated-71c115141be8) to obtain more insight. Let's review the general steps of this algorithm and suppose K and initial centers are set using some methods:

1. Measuring the distance between each sample and all centroids

2. The nearest center to each sample determines that sample's cluster

3. updating centroids

These three steps are iteratively performed until a convergence happens or specific numbers of loops are executed.

## DNN-based Implementation

With these aforementioned steps in mind, now the general algorithm of clustering with (DNN) is introduced. After selecting a proper K:

1. K samples are selected from the whole dataset which are the first centroids.

2. These K centroids are labeled with their cluster number and then fed to the DNN model. Then, based on the predicted cluster for each centroid and its actual cluster, the prediction error is computed by employig cross-entrooy loss function and the model's parameter are updataded using standard optimization methods such as gradient descent.

3. All samples now are fed into the model and per each sample, a predicted cluster number is obtained, which is an equivalent step for computing the most alike center for a sample in simple K-means.

4. Considering the new clusters obtained by the previous steps, the center of each cluster is obtained by averaging from all its members.

## Visulization

Below, you can find a simple illustration of the above method to get more insight into that.





https://user-images.githubusercontent.com/45314641/191182285-996d324e-2f6c-4e4d-b34f-2e36b6c3eb8c.mp4


