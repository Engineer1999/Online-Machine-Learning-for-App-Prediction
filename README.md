# Online Machine Learning for App Preloading 
Objective of this project is to decrease response time of the apps by preloading them.

In this project we have used supervised machine learning concept in operating systems.  We are using machine learning algorithm to enhance user experience by introducing a predictive model which can predict the applications likely to be opened next.  Using this prediction, operating system will configure the necessary files in advance and that will reduce the response time of that particular application.Proposed method will learn about application usage behaviour of user and it will provide a personalized service to each user according to their daily application usage behaviour.

### Approch 
To carry out the above mentioned task, we use Hoefding Tree Algorithm which comes in the category of online supervised machine learning algorithms. Any machine learning algorithm requires data to learn usage pattern of applications. We made a program which can generates the data. For this project, we consider the application usage pattern of one of our team member. Each user have diferent application usage behaviour, to address this issue we have use multi-threading, so model can learn the diferent users pattern and make prediction accordingly. Detail discussion is provided in subsequent sections.

### Data Genration
We have generated data for FireFox, Matlab, PDFviewer, PUBG, and VLC applications having features 'Internet', 'Minute', 'Hour', 'Weekday', 'Location', 'Audiocable'. For labelling the data we have used 32 labels(25) ,where each label shows which applications are open. For example if label is 5, then the binary representation of 5 (00101) shows that application 3 and application 5 are open.
First a pattern for each applications was decided in terms of above give features. 500 records were generated with above specications for each applications. Now same records might occur for two diferent applications indicating the case when both the applications are open, and so those rows have to to combined and labeled accordingly. Finally the combined dataset (with records <= 2500) is saved to a csv file. For the simplicity during the data generation process we have assumed that data follows uniform distribution.

## Hoeffding Tree Algorithm
A Hoeffding Tree algorithm is an incremental decision tree algorithm which comes into the category of supervised online machine learning algorithms. It's a one type of decision tree algorithm which support online learning. This algorithm allow an existing tree to be updated using only new individual data instances, without having to re-process past instances. This may be useful in situations where the entire dataset is not available when the tree is updated, the original data set is too large to process or the characteristics of the
data change over time.
This algorithm suits best for this project because it can provide the customization which is required to enhance user experience.

## Multi Threading
We are using multi-threading to provide a customization per user. Our method will contain 2 Hoefding tree models.
#### Decision maker
#### Back-end learning model
Decision maker will be used to take current decision according to the data provided. It will be working continuously in the background. Back-end model is used to learn users application usage pattern continuously. Required data will be collected continuously and after a certain amount of time it will be fitted to the back-end learning model and statistics of back-end model will be exchanged with decision making model. This approach will be useful in understanding of different users application usage pattern.

## Flow-Diagram
![Flow diagram](/images/OS_Diagram.png)


## Performance Analysis
![Flow diagram](/images/PA.PNG)

Above figure shows the comparison between response time during the different stages of learning. We have simulated a scenario where model is getting data after some particular time and it is being trained and test. We can clearly observe the decreased response time in all applications. Matlab's response time has become nearly zero because according to data matlab is used in very particular time with appropriate circumstance. Learning usage pattern of matlab is easy compare to other applications which can be infer from the results.



