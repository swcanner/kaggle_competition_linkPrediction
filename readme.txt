mohler_sub: same example code as what Mohler provided

glm_r: The homework - export the indices to R and use supervised learning on it to predict edges
	unfortunately, this didn't really work out as I didn't understand how the connections between
	tree elements worked in networkx because its very funky. I then ouputted it to a csv and created
	some R code

rf_index: I fixed the issues in the previous code and used a random forest on it

nn_index: Used a neural network to predict the same thing

rf_addFeat: I used a dotproduct, normalized dot product, and angle to calculate the connections

rf_addCov: Added the covariance and inverse covariance to the input features

rf_addKmeans: ran Kmeans and added a one hot encoding of the classes to the input features

rf_doubleKmeans: I created two runs of the kmeans, one with a small value and one with a larger value so that
	we can observe both coarse and fine grained features of the data

rf_addPca: Run PCA on the "features.csv" and append a number of the components to the input vector

rf_addSvd: Run SVD and add a number of the components to the input vector. The idea was that PCA and
	TruncatedSVD will have different parameters, since PCA is a very specific type of SVD and I can
	capture different details on this

nn_all: So I put those features and fed them into a neural net, which I think is one of the main thoughts behind
	the graph neural network? I was quite confused by the lecture and knowing I couldn't ask any questions
	during the competition, I just took a random stab at it. I also used the input vector to run a multitude
	of models which I included the results of in "cross_valid.csv" with 20% holdout. I compared the models
	in this way and worked to develop the NN better although, fun fact, that public competition acc on the NN
	yielded a private leaderboard ranking of .805, which is really disapointing because it wasn't selected by
	Kaggle as my top one. The models used were a random forest, neural network, SVM, and Kmeans, each tested
	with multiple parameters and kernels.

boost.pdf: I took the cross validation data I had and built a boosting algorithm on it, which performed very poorly.
	I also used it to create a stacked model that fed into a small neural network; however, that didn't perform
	well either unfortunately.



