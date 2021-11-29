# Fraudulent Website Detection
**ACM Research, Fall 2021**

![Fraudulent_Website_Detection_Research_Poster](https://user-images.githubusercontent.com/89321986/143796168-67d3015e-4519-477b-84ac-c74d1ee67be2.png)


## Abstract
When browsing the internet, it’s common for users to encounter various kinds of fraudulent websites disguised as fake giveaway websites, false security alerts, imitations of legitimate websites, or fake advertisements. Our objective was to develop multiple machine learning models to determine which approach would provide the most accurate fraud classifications. We designed several rules common among fraudulent website hyperlinks and implemented them in accordance with our models.

## Data

For our data, we used a variety of URLs to form a data set that contains a diverse group of fraudulent websites. We gathered our base set of benign, spam, phishing, malware, and defacement URLs from the University of New Brunswick. We collected additional phishing URLs from Phishtank and benign URLs from [faizann24’s GitHub](https://github.com/faizann24/Using-machine-learning-to-detect-malicious-URLs/tree/master/data) [1]. Out of a total of 651,191 URLs, we randomly selected a subset of 5,000 URLs that were representative of the master data set. 

<p align="center">
  <img width="508" height="440" src="https://user-images.githubusercontent.com/89321986/143798068-da9cd1f8-452e-4d97-b97f-68e7247c7c8f.png">
</p>


## Models
- Logistic Regression
  * We implemented a bag of words model to create another matrix representation of the dataset.
  * The two matrices were combined and processed by the logistic regression model that can be imported from Scikit-Learn’s library.
- Decision Tree
  * For the decision tree, our model uses the fourteen rules we created that help identify whether or not a URL might be fraudulent.
  * Once again, these rules were used to create a vector that represented each URL. Each vector was then added into our matrix, and then the matrix was processed by the decision tree model. 
- Support Vector Machine(SVM)
  * Just like our previously listed models, the support vector machine (SVM) model utilizes the 14 rules we created to generate an output. After the prepped URLs were mapped into a matrix, the SVM model took those data points and produced an optimal boundary line so that the common data points were grouped.
- Convolutional Neural Network(CNN)
  * In order to prepare the data for the neural network, we used the GloVe algorithm to create vector representations of the URLs[2]. 
  * These vectors act as the embeddings that get passed into the neural network. Next, using Keras, we created our neural network with an input layer, a hidden layer - three convolution layers, and an output layer of a single value. 
  * The model was compiled with Adam and then fit with a total of thirty epochs.

## Results                                 
Typically for classification problems, logistic regression is used to predict the class of an element because it focuses on the core relationships between variables. However, after evaluating the calculated metrics for each of our models, we determined that the CNN would be the best choice for real-world fraudulent website detection. The complex and ever-changing nature of fraudulent URLs demands a model that can quickly adapt, and CNN’s high accuracy and precision scores illustrate that the model will not be easily influenced by extreme outliers.
    
The decision tree model consistently underperformed in all of the benchmark categories. We determined that the reason behind the model’s poor performance was because it over-fitted the data (due to the tree being too deep and easily impacted by outliers). In future applications, we believe that using the Random Forest technique would improve the decision tree’s performance and lead to better results.

<p align="center">
  <img width="600" height="200" src="https://user-images.githubusercontent.com/89321986/143797666-8c159e70-2817-4f31-950d-d56a78b29bb5.png">
</p>
            

## Conclusion
Our work to determine which combination of models best classifies fraudulent websites has deepened our understanding of what a malicious URL constitutes. As individuals who have personally experienced fraudulent websites, we wanted to create an efficient detection model that accurately analyzed the extent of a URL’s deception. 
We are confident that we have achieved this goal, and we are optimistic our analysis will be used to benefit all users of the internet. We hope that future teams will utilize our findings to create new tools that will accurately detect fraudulent activity.

## Contributors
- [Aditi Mungale](https://github.com/aditi-mungale)
- [Frankie Flores](https://github.com/floresfrankie)
- [Kush Bhagat](https://github.com/KBush) (Partial Contribution)
- [Ryan Donaldson](https://github.com/legitatx) (Partial Contribution)
- [Dr. Rishabh Iyer](https://cs.utdallas.edu/people/faculty/iyer-rishabh/) - Faculty Advisor


## References

[1] : faizann24, “Using-machine-learning-to-detect-malicious-urls/data at master · Faizann24/using-machine-learning-to-detect-malicious-urls,” GitHub, Feb-2017. [Online]. Available: https://github.com/faizann24/Using-machine-learning-to-detect-malicious-URLs/tree/master/data. [Accessed: 13-Nov-2021].

[2] : J. Pennington, R. Socher, and C. D. Manning, “GloVe: Global Vectors for Word Representation,” Aug-2014. [Online]. Available: https://nlp.stanford.edu/projects/glove/. [Accessed: 13-Nov-2021].

[3] : M. Siddhartha, “Malicious urls dataset,” Kaggle, 23-Jul-2021. [Online]. Available: https://www.kaggle.com/sid321axn/malicious-urls-dataset. [Accessed: 13-Nov-2021].

[4] : Mitchellkrogza, “Mitchellkrogza/malicious-web-content-detection-using-machine-learning: Chrome extension for detecting phishing web sites,” GitHub, Jun-2019. [Online]. Available: https://github.com/mitchellkrogza/Malicious-Web-Content-Detection-Using-Machine-Learning. [Accessed: 13-Nov-2021]. 



