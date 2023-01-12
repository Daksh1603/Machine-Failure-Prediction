<img src="https://user-images.githubusercontent.com/90456255/212119220-29f38bfb-dec8-4326-9e06-3bbf9b2499e0.jpg" width="1600px" height="400px">

<p style="text-align: center;color:#FD6A02;font-size:25px;"><strong>Introduction</strong></p>

At any point in time , a machine might run into unprecedented conditions causing it to fail , which in turn raises the effective cost / loss for major companies .

In order to avoid such conditions, I decided to create a machine failure prediction which also classifies the type of defect .

<p style="text-align: center;color:#FD6A02;font-size:25px;"><strong>Data</strong></p>

The dataset consists of : 

- <em>time.csv</em> - this file contains continuous records of a single machine over the course of 1 month . These records are irregular in a sense that sometimes they are instanced at 500 milliseconds and sometimes at a gap of 8 hours . There were 2 types of defects notices namely Tungsten Inclusion and Porosity Defect . The dataset is highly imbalanced giving rise to high bias ( 850,000 instances ) 
 > In order to combat its imbalanced nature we either implement SMOTE analysis or exploit its high bias nature by traing a SVC with high hard margin classification (A very big value for the C hyperparameter) .
 
 <p style="text-align: center;color:#FD6A02;font-size:25px;"><strong>Methodology</strong></p>

1. <p style="color:#FD6A02">The first and foremost step is to understand the problem statement entirely and make important deductions based on the statement .</p>


	+ What are we trying to find out ? What other attributes mean and represent , their types .
  	+ What are the important factors affecting the following ?
 	+ Cleaning the data to make sure there is no irregularity . 
 
 
2. <p style="color:#FD6A02">Importing the required libraries .</p>

3. <p style="color:#FD6A02">Loading the data .</p>

+ The data is loaded into a dataframe .
 	
+ For further analysis of these data and how they correlate with each other , we can merge them and then analyse them further however , I usually extend this part to EDA and not in Loading the Data because the data we have just received might not be perfect . It is not right to make dedcutions without clearing your assumptions on the data and without cleaning it .



4. <p style="color:#FD6A02">Data Engineering</p>

	+ Time series dataset contains in it a lot of information . A lot of independent factors (day_of_week, day, month, hour...) and dependent factors (voltage_chg, current_mean, working_hours...) can be deduced . Hence carefull data engineering is an integral part of this porject .
	+ Further , cleaning and transforming the data further prerares it for EDA . 
 
   >  Do keep in mind that data transormation here doesn't refer to minmax scaling or normalization . Simply conversion of irregular attributes to derive more regular attributes ( for example : dict value from offer Data ) .


5. <p style="color:#FD6A02">Exploratory Data Anlaysis</p>

	+ The following step involves getting to know your data to your full extent . Here , I try and visualise the data in order to bring important deductions that may help me in developing my model more effeciently .
	+ The following part is taken care of and explained in the `ipynb file` .

6. <p style="color:#FD6A02">SMOTE Analysis</p>

	+ Dividing the data into respective subsets : training (for training the model), validation (for comparing the performance of various models) and test data (for comparing the performance of the final model) .
	+ In order to remove the imbalance in the dataset , we make use of an oversampling technique called SMOTE .

7. <p style="color:#FD6A02">Training and Comparing Models </p>

   + Training various models and comparing results of each on stand out validation data .
   + Hyperparameter tuning with the help of grid search CV using Kfold validation techniques .

8. <p style="color:#FD6A02">Verifying performance on Test Data </p>

   + Testing the final model on the test data and displaying the confusion matrix .

