# IoT_Enabled_Hybrid_ENN_DQN_Framework_For_Crop_Healthcare
This repository contains resources associated with the research paper titled **An IoT-Enabled Hybrid Deep Q-Learning and Elman Neural Network Framework for Proactive Crop Healthcare in the Agriculture Sector**. The research integrates two publicly available datasets and implements a hybrid model combining Elman Neural Network (ENN) and Deep Q-Learning (DQN) for proactive crop healthcare in the agricultural sector. 
The repository includes the following:

   **Datasets:** Both individual and combined datasets, which are essential for training and evaluating the proposed model.
   
   **Code:** This folder provides three Jupyter Notebook files (.ipynb) that cover the implementation of the ENN, DQN, and the hybrid approach.

   **Figures:** This folder provides most of the results presented in the paper. 

A detailed description of the working mechanism, methodology, and results of the research is included within the repository files.

## Model Setup and Execution Workflow
To run the model, follow the steps outlined below:

### Step 1: Download and Save Datasets
Download all the required datasets and save them to your local drive.

### Step 2: Combine Datasets (Optional)
While the combined dataset is already available in the dataset folder, you can review and understand the dataset combination process by using the Code/dataset_combining_process.ipynb file. Simply provide the paths to the individual datasets you saved in Step 1 and run the script.
If you prefer to use the pre-combined dataset, proceed directly to Step 3.

### Step 3: Download and Save the Pre-trained ENN Model
Download the pre-trained enn_model.h5 file, which contains the trained Elman Neural Network (ENN) model.
If you wish to retrain the ENN model, use the Code/ENN-Model.ipynb file. Provide the path to the combined dataset and specify the desired location to save the trained model before running the script.

### Step 4: Run the DQN Model
Once you have the combined dataset and the trained ENN model (enn_model.h5), load and run the Code/DQN-Model.ipynb script. Be sure to provide the path to the enn_model.h5 file.

### Step 5: Generate Results
Finally, run the subsequent code to obtain a summary of the optimal actions and plot the results.

# System Architecture
The architecture of the proposed model consists of several functional components. It begins with the Agricultural Field, where monitoring sensors are installed to collect health and environmental data of the crops. This IoT data is gathered and stored in databases, which are later used by the Elman Neural Network (ENN) to assess crop health. The results from the ENN are then fed into the Deep Q-Learning (DQN) model, which determines the optimal actions based on the crop health information provided by the ENN. The final output is utilized by farmers and agricultural technology companies to improve crop healthcare. An overview of the system model is presented in the following figure.
<p align="center">
<img src="https://github.com/shahid3167/IoT_Enabled_Hybrid_ENN_DQN_Framework_For_Crop_Healthcare/blob/main/Figures/SystemModel.jpg" width="700" height="600">
<p align="center">
  Fig.1.  System model of IoT-enabled hybrid (DQN and ENN) framework for managing agricultural field.

# Dataset Description and SMOTE Analysis
The extracted dataset is subsequently merged and is characterized as presented in Table 1. The categorical variable "crop health" is the output feature, while the remaining features are input features that collectively determine whether a crop is healthy or unhealthy. 
<p align="center">
<img src="https://github.com/shahid3167/IoT_Enabled_Hybrid_ENN_DQN_Framework_For_Crop_Healthcare/blob/main/Figures/Table%201.png" width="550" height="280">
<p align="center">

  # Data Eneginnering
A SMOTE anlysis is performed for class balancing and the results before SMOTE and after SMOTE is presented in Figure 2.  A correlation among the various features (excluding certain types such as object type, date time type, and binary type features) is presented in Figure 3. It highlights a strong correlation between potassium and phosphorus, while there is a weak relation of these two features with nitrogen. Following the feature relationship, a distribution of these features for the crop and fruit with mean and median values is provided in Figure 4. The figure indicates that the nitrogen, phosphorus, potassium, and rainfall are right-skewed
(positively skewed), while the temperature and pH follow normal distributions. In contrast, humidity has two peaks, thereby representing a bimodal distribution.
<p align="center">
<img src="https://github.com/shahid3167/IoT_Enabled_Hybrid_ENN_DQN_Framework_For_Crop_Healthcare/blob/main/Figures/DatasetBlanace.jpg" width="550" height="400">
<p align="center">
Fig. 2. A representation of class balancing through SMOTE analysis.

<p align="center">
<img src="https://github.com/shahid3167/IoT_Enabled_Hybrid_ENN_DQN_Framework_For_Crop_Healthcare/blob/main/Figures/CorelationMatrix.jpg" width="600" height="400">
<p align="center">
Fig. 3. Pearson’s correlation measures highlighting a linear relationship among the features.

<p align="center">
<img src="https://github.com/shahid3167/IoT_Enabled_Hybrid_ENN_DQN_Framework_For_Crop_Healthcare/blob/main/Figures/Features.jpg" width="1000" height="500">
<p align="center">
Fig. 4. A distribution of different features as a function of the crop and fruit, highlighting the mean and median representations.

  # Results
  ## Elman Neural Network Results
  The training and testing loss function (Figure 5 (a)) and the training and testing accuracy (Figure 5 (b)) over a sample of 500 iterations demonstrate that the ENN-DQN effectively understands the underlying patterns in the data, successfully avoiding both overfitting and underfitting issues.
<p align="center">
<img src="https://github.com/shahid3167/IoT_Enabled_Hybrid_ENN_DQN_Framework_For_Crop_Healthcare/blob/main/Figures/LossAccuracyPerformance.jpg" width="1000" height="400">
<p align="center">
Fig. 5. Training and testing performance evaluation of the proposed ENN-DQN. (a). Training and testing loss function, (b). Training and testing accuracy.

Following the underfitting and overfitting criteria, the performance of the proposed ENN-DQN is evaluated by incorporating different Gaussian noise ratios in the dataset. The injection of these different noise ratios results in the introduction of different levels of heterogeneity in the dataset. Consequently, a robustness evaluation of accuracy, precision, recall, and F-score with different levels of heterogeneity: no noise (i.e., 0% noise level), low noise (i.e., 30% noise level), medium noise (i.e., 50% noise level), and high noise (i.e., 100% noise level) is presented in Figure 6.
<p align="center">
<img src="https://github.com/shahid3167/IoT_Enabled_Hybrid_ENN_DQN_Framework_For_Crop_Healthcare/blob/main/Figures/PerformanceWithNoises.jpg" width="1000" height="800">
<p align="center">
Fig. 6. Robustness evaluation of the proposed ENN-DQN model under varying noise ratios: no noise (0%), low noise (30%), medium noise (50%), and high noise (100%) for (a) Accuracy, (b) Precision, (c) Recall, and (d) F-score.

Area under the curve (AUC) and confusion matrics for different epoches are presented in Figure 7 and Figure 8. 
<p align="center">
<img src="https://github.com/shahid3167/IoT_Enabled_Hybrid_ENN_DQN_Framework_For_Crop_Healthcare/blob/main/Figures/AUC.jpg" width="550" height="400">
<p align="center">
Fig. 7. A representation of area under the curve (AUC).

<p align="center">
<img src="https://github.com/shahid3167/IoT_Enabled_Hybrid_ENN_DQN_Framework_For_Crop_Healthcare/blob/main/Figures/ConfusionMatrix.jpg" width="1000" height="800">
<p align="center">
Fig. 8. Confusion matrix for different epochs.

  ## Deep Q-Learning Results
  Deep Q-learning perform optimal action based on the rewards. These actions includes **Do Nothing**, **Irregation**, **Fertilize**, **Ventilate**, **Irregation and Fertilize**, **Irregation and Ventilate**, **Fertilize and Pesticide**, **Pesticide or Fungcide**, and **Request for Manual Check**. The rewards and the optimal different actions are presented in Figure 9 and Figure 10.
<p align="center">
<img src="https://github.com/shahid3167/IoT_Enabled_Hybrid_ENN_DQN_Framework_For_Crop_Healthcare/blob/main/Figures/TotalRewards.png" width="1000" height="400">
<p align="center">
Fig. 9. A representation of the reward function with different moving average.

<p align="center">
<img src="https://github.com/shahid3167/IoT_Enabled_Hybrid_ENN_DQN_Framework_For_Crop_Healthcare/blob/main/Figures/OptimizedAction.png" width="1000" height="400">
<p align="center">
Fig. 10. A representaiton of the different optimal actions.

  ## Statistical Results
A statistical analysis with a 95% confidence interval is performed for a sample size of 30 epochs to verify the quantitative analysis. A detailed comparison of the statistical analysis for the various methods is presented in Table 4. Following the importance of the pattern, we further validated the statistical analysis by computing the average of the performance metrics with a 95% CI for the various methods, as presented in Figure 11 and 12. 
<p align="center">
<img src="https://github.com/shahid3167/IoT_Enabled_Hybrid_ENN_DQN_Framework_For_Crop_Healthcare/blob/main/Figures/Table4.png" width="800" height="600">
<p align="center">

<p align="center">
<img src="https://github.com/shahid3167/IoT_Enabled_Hybrid_ENN_DQN_Framework_For_Crop_Healthcare/blob/main/Figures/Average-Analysis.jpg" width="1000" height="300">
<p align="center">
Fig. 11. A representation of the statistical analysis.

<p align="center">
<img src="https://github.com/shahid3167/IoT_Enabled_Hybrid_ENN_DQN_Framework_For_Crop_Healthcare/blob/main/Figures/Average-Analysis-BoxPlot.jpg" width="1000" height="600">
<p align="center">
Fig. 11. Box plot for validating statistical analysis.




# Contact details
### Dr. Shahid Hussain (shahid.hussain@atu.ie)
### Affiliation:
**Atlantic Technological University (ATU), Dublin Road, Galway, H91 T8NW, Ireland**

# Paper: 
### This code is related to the following paper, which can be cited as:
M. Alazmi et al., "An IoT-Enabled Hybrid Deep Q-Learning and Elman Neural Network Framework for Proactive Crop Healthcare in the Agriculture Sector," Internet of Things, 2025.
