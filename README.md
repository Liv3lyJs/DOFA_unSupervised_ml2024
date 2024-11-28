Author: Jean-Sébastien Giroux
Date: 2023-2024
Subject: Final Bachelor's Project at Sherbrooke University (Computational and Electrical Engineering)
Description: The goal of the project is to use an unsupervised network to identify defects in welding pieces.
             The main idea of the project is as follows: We train a network using only healthy pieces, to which 
             we artificially add defects represented by either a black rectangle or a black circle. The network 
             is trained with these defect-added pieces as input data, while the target remains the original defect-free pieces. 
             This setup enables the network to learn how to reproduce defect-free welding pieces.

             For classification, the trained network will process data containing both defect-free and defective pieces. 
             Once the network infers a reconstructed image of a welding piece, we will analyze loss metrics such as RMSE, MAE, or SSIM 
             by comparing the original image with the network's prediction.

             We expect the loss metrics to be higher for pieces containing defects and lower for defect-free pieces, as the network is trained 
             to reconstruct healthy samples. Based on a predefined threshold, we will determine whether a piece contains a defect or not.

             This workflow leverages the network's ability to distinguish between healthy and defective welding pieces by analyzing its reconstruction performance.
Libraries: pip install python
           pip install tensorflow
           pip install numpy 
           pip install matplotlib
           pip install keras-tuner
Code Structure: To launch training or perform a hyperparameter search, run the train.sh script in the terminal. This batch file sets the initial variables and constants 
                and creates the virtual environment (useful for running on computer clusters). To launch a test, follow a similar process but use the test.sh script instead. 
                This script initializes the variables, constants, and virtual environment, then calls test.py to perform the classification.
                This setup ensures a clear and modular workflow for training and testing your model.

                train.sh : Bash file to select variables and constants, create virtual environment and lanch train.py
                train.py: Main file to train and do a hyper-parameter search for a selected model
                data_processing.py: Class where the data processing is done (Ideally, data processing is done only once for one dataset (Save data after this to save time and resources))
                callbacks.py: Class of callbacks used in the training of the neural network to help training if certain conditions are met.
                hyper_parameters_tuner.py: Class to do the hyper-parameter search with Keras-Tuner.
                model.py: Class where the neural networks models are defined. 
                training_info.py: Wehere graph during training are done and saved. 
                test.sh: Bash file to select variables and constants, create virtual environment and lanch test.py.
                test.py: Do the Neural Network inference on the test data and classify the welding results. 
                
  
                 
