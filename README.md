# WineQualityPred
 ## Prediction:

 The objective of this project is to develop a Python application utilizing the PySpark framework, operating within an Amazon Web Services (AWS) Elastic MapReduce (EMR) cluster. Its primary aim is to concurrently train a machine learning model on EC2 instances for predicting wine quality using publicly available data. Post-training, the model is leveraged for making predictions on wine quality. To streamline deployment, Docker is employed to construct a container image for the trained model.

## Steps:

1. Sign in to the AWS Management Console: Go to https://aws.amazon.com/ and sign in to the AWS Management Console using your credentials.
<br>
2.Navigate to the EC2 Dashboard: Once logged in, navigate to the EC2 Dashboard by searching for "EC2" in the AWS services search bar and selecting it.

3.Choose "Key Pairs": In the EC2 Dashboard, locate the "Network & Security" section in the left-hand navigation pane, and then select "Key Pairs".
4.Create Key Pair: Click on the "Create Key Pair" button.
5.Enter Key Pair Name: Provide a name for your key pair.
6.Download Key Pair: predkey.pem.
7.Then go to EMR console and create EMR cluster 
8.4. Creating the spark in the AWS instance by using EMR console: 
9.Creating the spark cluster by using the EMR console, and create the 4 instances: 
10.Name and application: 
        Amazon EMR release: emr-5.33.0 
            Application bundle: Hadoop 2.10.1 Spark 2.4.7, Zippeline 0.9.0, and Yarn 

By following images, we need to create EMR Cluster:
![image](https://github.com/Snehardhi24/WineQualityPred/assets/150552754/03151c6e-2b6e-43d3-b204-2ca83004be9c)

![image](https://github.com/Snehardhi24/WineQualityPred/assets/150552754/4e60ce24-72b8-41a9-849e-70d8d911260e)

![image](https://github.com/Snehardhi24/WineQualityPred/assets/150552754/1e0b7755-fae4-4c8e-99f2-d55d91db034a)

![image](https://github.com/Snehardhi24/WineQualityPred/assets/150552754/a181f746-7071-41ac-b751-7c34c0a495a2)

![image](https://github.com/Snehardhi24/WineQualityPred/assets/150552754/eb10b2c9-c8cf-415c-824e-7fc29c9162ec)

## Running AWS in CMD(Without Docker):

predkey.pem" ec2-user@ec2-107-21-138-81.compute-1.amazonaws.com
We used this for connecting the ssh pair to ec2 cluster. 
We used sudo su for switch user case for EMR.

![image](https://github.com/Snehardhi24/WineQualityPred/assets/150552754/8313df03-60f7-4cc0-bb36-434436288397)

We took our code Predictions.py file from s3 bucket.
We can observe that spark file on port 41669.

![image](https://github.com/Snehardhi24/WineQualityPred/assets/150552754/d4a1a482-5d1a-4a09-84e5-2ff3b2c99c66)

![image](https://github.com/Snehardhi24/WineQualityPred/assets/150552754/0ef60d13-7335-42a8-9d22-af718d8014df)

## With Docker:

- Enter your credentials
- Navigate to the folder containing the Docker file. This folder should also contain the model, Predictions.py, and the dataset to be used for prediction.
- Build this docker image with:
             docker build -t predtest .

  ![image](https://github.com/Snehardhi24/WineQualityPred/assets/150552754/796526dc-9e4d-4ac1-9184-5e97106791e0)

- Push this image to Docker Hub with:
 docker push sd22851/winequlpred

![image](https://github.com/Snehardhi24/WineQualityPred/assets/150552754/6aa32868-63a6-4b75-9414-b4f2a2595b4a)

![image](https://github.com/Snehardhi24/WineQualityPred/assets/150552754/be33e272-70b2-4578-a3fe-c7f2a31295c7)
