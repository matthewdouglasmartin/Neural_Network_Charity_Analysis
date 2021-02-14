# Neural_Network_Charity_Analysis
## Machine Learning and Neural Networks
### Overview of the analysis:

A binary classifier was developed that utilizes machine learning and neural networks to determine whether applicants within a provided dataset, would be successful if provided funding.  The dataset provided contains about 34,000 organizations with 12 columns of data for each organization.  Initially the deep learning neural network model that was used consisted of running the model for 100 epochs and 2 hidden layers. In an effort to optimize the model it was then run for 150 epochs and more nodes per hidden layer.  Both attempts to get the model to perform above 73% accuracy were unsuccessful.    

### Results:

* Data Preprocessing
  * The "IS_SUCCESSFUL" column is considered the target for this model.  
  * The "APPLICATION_TYPE", "AFFILIATION", "CLASSIFICATION", "USE_CASE", "ORGANIZATION", "STATUS", "INCOME_AMT", "SPECIAL_CONSIDERATIONS", and "ASK_AMT" columns are considered the features for this model.  
  * The "EIN" and "NAME" columns were dropped and do not belong to the target or features.

* Compiling, Training, and Evaluating the Model
  * When working to optimize this model adjustments were made to the neurons, layers and activation functions in an effort attain an accuracy score above 75%.  
    *  **Initial Model** [Initial_Model](https://github.com/matthewdouglasmartin/Neural_Network_Charity_Analysis/blob/main/Resources/Initial_Model.png) 
      * Initially, the model was constructed with 80 neurons for the first layer and 30 neurons for the second layer.  The two hidden layers both used relu activation functions, while the output layer used the sigmoid activation function.
  * The initial model was able to perform at 72.9% accuracy which did not meet the requirements of the model performing at a minimum of 75%.  
  * These steps were taken in an effort to improve the initial model:
    *  **Optimized Model** [Optimized_Model](https://github.com/matthewdouglasmartin/Neural_Network_Charity_Analysis/blob/main/Resources/Optimized_Model.png)
      * For the optmized model, the first hidden layer consisted of 120 neurons and the second consisted of 80.  Each layers neurons were increased to be three times and two times the amount of features within the dataset in hopes of giving the model more opportunities to learn from the dataset.  There were only two hidden layers used and they both used the tanh activation function.  The output layer used the sigmoid activation function.  The number of hidden layers was kept at 2 in hopes of preventing the model from overfitting to the dataset.  Regarding the selection of the activation function for the hidden layers, tanh was selected with an understanding that it performs well with larger datasets.

### Summary:

Overall, the initial and "optimized" models performed very similarly even though the aforementioned adjustments were made.  The first model achieved a 72.9% accuracy while the second had a very slight improvement and was able to perform with 73.1% accuracy.  A different model aside from these two would be needed in order to achieve a base accuracy of 75%.  One suggestion would to further process the dataset provided and remove any other distruptive columns or reasses the binning conducted on some of the categorical variables.  Anoher option would be to add another hidden layer for a total of three in an effort to help the model learn more from the dataset and predict more accurately.  Finally, changing the activation functions to ones that are better suited to learn from the dataset.