# Fetal-Health-Classification-Model

             Cardiotocography (CTG) is used during pregnancy to monitor fetal heart rate and uterine contractions. It is monitor fetal well-being and allows early detection of fetal distress. 

    CTG interpretation helps in determining if the pregnancy is high or low risk.  An abnormal CTG may indicate the need for further investigations and potential intervention.

    In this project, I will create a model to classify the outcome of Cardiotocogram test to ensure the well being of the fetus. 

 Step 1: IMPORTING LIBRARIES

 Step 2: LOADING DATA

         On This Dataset
         
         Cardiotocograms (CTGs)** are a simple and cost accessible option to assess fetal health, allowing healthcare professionals to take action in order to prevent child and maternal mortality. The equipment itself works by sending ultrasound pulses and reading its response, thus shedding light on fetal heart rate (FHR), fetal movements, uterine contractions and more.

         This dataset contains 2126 records of features extracted from Cardiotocogram exams, which were then classified by expert obstetrician into 3 classes:

            1. Normal
            2. Suspect
            3. Pathological

 Step 3: DATA ANALYSIS
        
         The analysis consist of:
           Count Plot
           Corelation Heat Map
           Implot
           Swarm And Boxen Plot

         first of all let us evaluate the target and find out if our data is imbalanced or not

         The count plot of targets indicates an imbalance in data. This is a case that tends to provide misleading classification accuracy. 

         The performance measures that would provide better insight:
           Confusion Matrix
           Precision
           Recall
           F1 Score 

         Let us evaluate the correlation matrix.

         Based on the correlation matix, it is clear that "accelerations","prolongued_decelerations", "abnormal_short_term_variability", "percentage_of_time_with_abnormal_long_term_variability" and "mean_value_of_long_term_variability" are the features with higher correlation with fetal_health. Let's have a closer look at these with fetal_movement on y axis. This will provide a clearer picture of trends that indicate fetus health. 

         Accelerations Vs Fetal Movement by Fetal Health

         Prolongued Decelerations Vs Fetal Movement by Fetal Health

         Abnormal Short Term Variability Vs Fetal Movement by Fetal Health

         Mean Value Of Long Term Variability Vs Fetal Movement by Fetal Health**

         We can see the rates of change of the above-mentioned values with each target show a specific trend. 
         
         We can also spot outliers. Let's have a look at outliers on a more suitable plot.

         columns for detailed visualisation
         
         I spotted outliers on our dataset. However, it is not quite a good idea to remove them yet as it may lead to overfitting. Though we may end up with better statistics. 

         A basic rule of thumb for the outliers in question is:

         It is a measurement error or data entry error, correct the error if possible. If you can’t fix it, remove that observation. In our case, this is the outcome of a CTG report so it is unlikely that this was a data entry error. 

         If it is not a part of the population you are studying, you can legitimately remove the outlier. In this case, this all is about the fetus, and experts tag the classification. Let's stick with the expert opinion. 

         Thus assuming that these are the natural part of the population we are studying, we should not remove it.

         The above plot shows the range of our feature attributes. All the features are in different ranges. To fit this in a model we must scale it to the same range.

In the model building, we will preprocess the features to do the same.

Step 4: MODEL SELECTION AND BUILDING

        In this section we will:
        
           Set up features(X) and target(Y)
          
          Scale the features
          
          Split training and test sets 
          
          Model selection
          
          Hyperparameter tuning

       assigning values to features as X and target as y
       
       spliting test and training sets
       
       A quick model selection process
       
       pipelines of models( it is short was to fit and pred)

       List of all the pipelines

       Dictionary of pipelines and classifier types for ease of reference

       Fit the pipelines

       cross validation on accuracy 

       So Random Forest does best amongst the models to be the most accurate. Let us build a better random forest with grid search cv.
Let's find out how it performs on testset

       taking look at the test set

       Building a dictionalry with list of optional values that will me analyesed by GridSearch CV

       Fitting the trainingset to find parameters with best accuracy

       Getting the outcome of gridsearch

       cofusion matrix
       
