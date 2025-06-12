# IoT_Enabled_Hybrid_ENN_DQN_Framework_For_Crop_Healthcare
This repository contains resources associated with the research paper titled **An IoT-Enabled Hybrid Deep Q-Learning and Elman Neural Network Framework for Proactive Crop Healthcare in the Agriculture Sector**. The research integrates two publicly available datasets and implements a hybrid model combining Elman Neural Network (ENN) and Deep Q-Learning (DQN) for proactive crop healthcare in the agricultural sector. 
The repository includes the following:

   **Datasets:** Both individual and combined datasets, which are essential for training and evaluating the proposed model.
   
   **Code:** The repository provides three Jupyter Notebook files (.ipynb) that cover the implementation of the ENN, DQN, and the hybrid approach.

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

# Dataset Description
The extracted dataset is subsequently merged and is characterized as presented in Table 1. The categorical variable "crop health" is the output feature, while the remaining features are input features that collectively determine whether a crop is healthy or unhealthy.
<p align="center">
<img src="https://github.com/shahid3167/IoT_Enabled_Hybrid_ENN_DQN_Framework_For_Crop_Healthcare/blob/main/Figures/Table%201.jpg" width="450" height="200">
<p align="center">

  # Data Eneginnering
  A correlation among the various features (excluding certain types such as object type, date time type, and binary type features) is presented in Figure 2. It highlights a strong correlation between potassium and phosphorus, while there is a weak relation of these two features with nitrogen. Following the feature relationship, a distribution of these features for the crop and fruit with mean and median values is provided in Figure 3. The figure indicates that the nitrogen, phosphorus, potassium, and rainfall are right-skewed
(positively skewed), while the temperature and pH follow normal distributions. In contrast, humidity has two peaks, thereby representing a bimodal distribution.
<p align="center">
<img src="https://github.com/shahid3167/IoT_Enabled_Hybrid_ENN_DQN_Framework_For_Crop_Healthcare/blob/main/Figures/CorelationMatrix.jpg" width="600" height="400">
<p align="center">

<p align="center">
<img src="https://github.com/shahid3167/IoT_Enabled_Hybrid_ENN_DQN_Framework_For_Crop_Healthcare/blob/main/Figures/Table%201.jpg" width="450" height="200">
<p align="center">

  
© 2025 **Atlantic Technological University, Ireland**. All rights reserved. This code is part of the paper titled "**An IoT-Enabled Hybrid Deep Q-Learning and Elman Neural Network Framework for Proactive Crop Healthcare in the Agriculture Sector**," which is currently under review in the **Internet of Things journal (Elsevier)**. Unauthorized use, reproduction, or distribution of this code without permission is prohibited.
