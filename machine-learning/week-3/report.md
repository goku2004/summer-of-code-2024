Learned abboout machine learning techniques for unsupervised learning and their implementations.
The main step was to group the data in such a way that meaningful clusters can be obtained. I decided to group the data according to customers so customer behaviour can be observed and clustered. However we could also have chosen to group by different products and split those products in different categories. This could have been done by KMeans clustering as well. However TF-IDF vectorization method could have been used to work on the description of the product to categorize it into different types.
And then apply cosine similarity to filter out similarities between products and make clusters baes on their similarities. 
However currently I used Kmeans cluster to find clusters of customer that have done transactions in our store and made features based on that. There were many challenges in the dataset cleaning process because there were many edge cases to be covered like cancelation transactions having no buy order or unit price of some products being 0 which could potentially create noise in our data and filtering them out took some time. 
There was also feature engineering to be done like which features were important and which I could think off the top of my head. I had an issue in the elbow method and silhouette score initially because I had chosen not to scale all feeatures due to them being categorical. However that created wrong clusters which were either too imbalanced or almost too similar. 
I also tried DBscan however it was only creating a single cluster and a noise cluster for any value of min_points or eps values i took. So I didnt make that model.
Also for the recommendation system I tried to use assoication methods like FPtree however it took too much time and my computer started lagging so I decided to stick to a normal model based on clusters and the most bought products.
However I have learned the implementation and a little bit of math of all the methods stated above.