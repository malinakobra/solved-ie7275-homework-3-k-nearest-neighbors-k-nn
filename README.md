Download Link: https://assignmentchef.com/product/solved-ie7275-homework-3-k-nearest-neighbors-k-nn
<br>
<h1>Task 1: Tutorial</h1>

<ul>

 <li>Practice R models presented in “R Code for Textbook Examples in Chap 7 and 8.pdf.” For your convenience, the data sets referenced in the document are included the Homework folder.</li>

</ul>

<h1>Chapter 7: k-Nearest-Neighbors (k-NN)</h1>

<h2>Problem 7.1</h2>

<u>Personal Loan Acceptance</u>. Universal Bank is a relatively young bank growing rapidly in terms of overall customer acquisition. The majority of these customers are liability customers (depositors) with varying sizes of relationship with the bank. The customer base of asset customers (borrowers) is quite small, and the bank is interested in expanding this base rapidly to bring in more loan business. In particular, it wants to explore ways of converting its liability customers to personal loan customers (while retaining them as depositors).

A campaign that the bank ran last year for liability customers showed a healthy conversion rate of over 9% success. This has encouraged the retail marketing department to devise smarter campaigns with better target marketing. The goal is to use k-NN to predict whether a new customer will accept a loan offer. This will serve as the basis for the design of a new campaign.

The file <strong>UniversalBank.csv</strong> contains data on 5000 customers. The data include customer demographic information (age, income, etc.), the customer’s relationship with the bank (mortgage, securities account, etc.), and the customer response to the last personal loan campaign (Personal Loan). Among these 5000 customers, only 480 (= 9.6%) accepted the personal loan that was offered to them in the earlier campaign.

Partition the data into training (60%) and validation (40%) sets.

<ol>

 <li>Consider the following customer: Age = 40, Experience = 10, Income = 84, Family = 2, CCAvg = 2, Education_1 = 0, Education_2 = 1, Education_3 = 0, Mortgage = 0, Securities Account = 0, CD Account = 0, Online = 1, and Credit Card = 1. Perform a k-NN classification with all predictors except ID and ZIP code using k = 1. Remember to transform categorical predictors with more than two categories into dummy variables first. Specify the success class as 1 (loan acceptance), and use the default cutoff value of 0.5. How would this customer be classified?</li>

 <li>What is a choice of k that balances between overfitting and ignoring the predictor information?</li>

 <li>Show the confusion matrix for the validation data that results from using the best k.</li>

 <li>Consider the following customer: Age = 40, Experience = 10, Income = 84, Family = 2, CCAvg = 2, Education_1 = 0, Education_2 = 1, Education_3 = 0, Mortgage = 0, Securities Account = 0, CD Account = 0, Online = 1 and Credit Card = 1. Classify the customer using the best k.</li>

 <li>Repartition the data, this time into training, validation, and test sets (50% : 30% : 20%). Apply the k-NN method with the k chosen above. Compare the confusion matrix of the test set with that of the training and validation sets. Comment on the differences and their reason.</li>

</ol>

<h2>Problem 7.2</h2>

<u>Predicting Housing Median Prices</u>. The file <strong>BostonHousing.csv</strong> contains information on over 500 census tracts in Boston, where for each tract multiple variables are recorded. The last column (CAT.MEDV) was derived from MEDV, such that it obtains the value 1 if MEDV &gt; 30 and 0 otherwise. Consider the goal of predicting the median value (MEDV) of a tract, given the information in the first 12 columns.

Partition the data into training (60%) and validation (40%) sets.

<ol start="5">

 <li>Perform a k-NN prediction with all 12 predictors (ignore the CAT.MEDV column), trying values of k from 1 to 5. Make sure to normalize the data, and choose function <strong>knn</strong>() from package class rather than package FNN. To make sure R is using the class package (when both packages are loaded), use <strong>class::knn</strong>(). What is the best k? What does it mean?</li>

 <li>Predict the MEDV for a tract with the following information, using the best k:</li>

 <li>If we used the above k-NN algorithm to score the training data, what would be the error of the training set?</li>

 <li>Why is the validation data error overly optimistic compared to the error rate when applying this k-NN predictor to new data?</li>

 <li>If the purpose is to predict MEDV for several thousands of new tracts, what would be the disadvantage of using k-NN prediction? List the operations that the algorithm goes through in order to produce each prediction.</li>

</ol>




<h1>Chapter 8: The Naïve Bayes Classifier</h1>

<h2>Problem 8.1</h2>

<u>Personal Loan Acceptance</u>. The file <strong>UniversalBank.csv</strong> contains data on 5000 customers of Universal Bank. The data include customer demographic information (age, income, etc.), the customer’s relationship with the bank (mortgage, securities account, etc.), and the customer response to the last personal loan campaign (Personal Loan). Among these 5000 customers, only 480 (= 9.6%) accepted the personal loan that was offered to them in the earlier campaign. In this exercise, we focus on two predictors: Online (whether or not the customer is an active user of online banking services) and Credit Card (abbreviated CC below) (does the customer hold a credit card issued by the bank), and the outcome Personal Loan (abbreviated Loan below).

Partition the data into training (60%) and validation (40%) sets.

<ol>

 <li>Create a pivot table for the training data with Online as a column variable, CC as a row variable, and Loan as a secondary row variable. The values inside the table should convey the count. In R use functions <strong>melt</strong>() and <strong>cast</strong>(), or function <strong>table</strong>().</li>

 <li>Consider the task of classifying a customer who owns a bank credit card and is actively using online banking services. Looking at the pivot table, what is the probability that this customer will accept the loan offer? [This is the probability of loan acceptance (Loan = 1) conditional on having a bank credit card (CC = 1) and being an active user of online banking services (Online = 1)].</li>

 <li>Create two separate pivot tables for the training data. One will have Loan (rows) as a function of Online (columns) and the other will have Loan (rows) as a function of CC.</li>

 <li>Compute the following quantities [P(A B) means “the probability of A given B”]:

  <ol>

   <li>P(CC = 1 Loan = 1) (the proportion of credit card holders among the loan acceptors)</li>

   <li>P(Online = 1 Loan = 1)</li>

  </ol></li>

</ol>

<ul>

 <li>P(Loan = 1) (the proportion of loan acceptors) iv. P(CC = 1  Loan = 0)</li>

</ul>

<ol>

 <li>P(Online = 1 Loan = 0)</li>

 <li>P(Loan = 0)</li>

</ol>

<ol>

 <li>Use the quantities computed above to compute the naive Bayes probability P(Loan = 1 CC = 1, Online = 1).</li>

 <li>Compare this value with the one obtained from the pivot table in (b). Which is a more accurate estimate?</li>

 <li>Which of the entries in this table are needed for computing P(Loan = 1 CC = 1, Online =</li>

</ol>

1)? In R, run naive Bayes on the data. Examine the model output on training data, and

find the entry that corresponds to P(Loan = 1  CC = 1, Online = 1). Compare this to the number you obtained in (e).




<h2>Problem 8.2</h2>

<u>Automobile Accidents</u>. The file <strong>Accidents.csv</strong> contains information on 42,183 actual automobile accidents in 2001 in the United States that involved one of three levels of injury: NO INJURY, INJURY, or FATALITY. For each accident, additional information is recorded, such as day of week, weather conditions, and road type. A firm might be interested in developing a system for quickly classifying the severity of an accident based on initial reports and associated data in the system (some of which rely on GPS-assisted reporting).




Our goal here is to predict whether an accident just reported will involve an injury (MAX_SEV_IR = 1 or 2) or will not (MAX_SEV_IR = 0). For this purpose, create a dummy variable called INJURY that takes the value “yes” if MAX_SEV_IR = 1 or 2, and otherwise “no.”




<ol>

 <li>Using the information in this dataset, if an accident has just been reported and no further information is available, what should the prediction be? (INJURY = Yes or No?) Why?</li>

 <li>Select the first 12 records in the dataset and look only at the response (INJURY) and the two predictors WEATHER_R and TRAF_CON_R.

  <ol>

   <li>Create a pivot table that examines INJURY as a function of the two predictors for these 12 records. Use all three variables in the pivot table as rows/columns.</li>

   <li>Compute the exact Bayes conditional probabilities of an injury (INJURY = Yes) given the six possible combinations of the predictors.</li>

  </ol></li>

</ol>

<ul>

 <li>Classify the 12 accidents using these probabilities and a cutoff of 0.5.</li>

</ul>

<ol>

 <li>Compute manually the naive Bayes conditional probability of an injury given WEATHER_R = 1 and TRAF_CON_R = 1.</li>

 <li>Run a naive Bayes classifier on the 12 records and two predictors using R. Check the model output to obtain probabilities and classifications for all 12 records. Compare this to the exact Bayes classification. Are the resulting classifications equivalent? Is the ranking (= ordering) of observations equivalent?</li>

</ol>

<ol>

 <li>Let us now return to the entire dataset. Partition the data into training (60%) and validation (40%).

  <ol>

   <li>Assuming that no information or initial reports about the accident itself are available at the time of prediction (only location characteristics, weather conditions, etc.), which predictors can we include in the analysis? (Use the Data_Codes sheet.)</li>

   <li>Run a naive Bayes classifier on the complete training set with the relevant predictors (and INJURY as the response). Note that all predictors are categorical. Show the confusion matrix.</li>

  </ol></li>

</ol>

<ul>

 <li>What is the overall error for the validation set?</li>

</ul>

<ol>

 <li>What is the percent improvement relative to the naive rule (using the validation set)?</li>

 <li>Examine the conditional probabilities output. Why do we get a probability of zero for P(INJURY = No SPD_LIM = 5)?</li>

</ol>




<strong>Files Included in the Folder: </strong>

<ol>

 <li><strong>Homework 3.pdf </strong></li>

 <li><strong>R Code for Textbook Examples in Chap 7 and 8.pdf </strong></li>

</ol>

<h3>3. Accidents.csv 4. BostonHousing.csv</h3>

<ol start="5">

 <li><strong>UniversalBank.csv </strong></li>

</ol>