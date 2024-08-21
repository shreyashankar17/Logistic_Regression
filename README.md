# LOGISTIC REGRESSION

Logistic Regression is commonly used to estimate the probability that an instance belongs to a particular class.If the estimated probability is greater than 50% then the model predicts that the instance belongs to that class(called the positive class ,labeled as '1') or else it predict that it does not
(that is it belongs to the negative class ,labeled as 'o' ).This make it a binary classifier

*Equation of Logistic Regression is * Y= Wt x + B i.e y is equal to W to the power of t plus b

![image](https://github.com/user-attachments/assets/e9fd5c18-7fff-4845-9349-fadca9a3a91d)

Now lets consider above figure, where red is our negative class and green is our positive class.

##### Step to calculate best fit line

Consider our line is passing through origin then our b(intercept) will be zero and equation will be Y=Wt * X

Now in linear algebra if you want to calculate the distance between point and plane

Distance between plane and point

![image](https://github.com/user-attachments/assets/eae805e3-2e18-4488-ae5c-dd425f231846)

Since we assume our line is passing through origin then our b=0

![image](https://github.com/user-attachments/assets/73d89e8c-dbd7-4054-886d-0cd24b2a836e)

And if we consider W as a unit vector then |w|=1

![image](https://github.com/user-attachments/assets/7c7809f5-8648-4074-8f24-ec2ae9382667)


Now we have many data point around the plane then our equation will be

![image](https://github.com/user-attachments/assets/8b4ec2ac-69b7-4d9d-ac76-8a9959eaefd3)

The sum of distance between all the point and plane.

Points above the plane are positive points(green=postive).

Distance of green points from the plane will be positive.

Points below the plane are negative points(red=negative).

Distance of red points from the plane will be negative

###### CASE-1

Lets calculate the distance of green point(which is above the plane) form the plane
![image](https://github.com/user-attachments/assets/299d583a-2cec-4ff3-a8b9-428ce1489712)
Suppose "A" is that point and green line indicate the distance between plane and point "A" Screenshot (12).png

point "A" is positive and distance between plane and point is positive (above the plane)

![image](https://github.com/user-attachments/assets/e2ff36f9-8f9d-485c-aa24-da284fa6cc35)

In above equation you can see that distance is positive and point is also positive

![image](https://github.com/user-attachments/assets/d5f336db-82c4-40e8-8528-cdd52ddb112d)

The product of this multiplication will always greater than zero i.e value will positive always that's means correctly classified

###### CASE-2

Lets calculate the distance of red point(which is below the plane) form the plane
![image](https://github.com/user-attachments/assets/306b957c-cc8a-4eb1-8de7-5260f40e5147)
Suppose "B" is that point and red line indicate the distance between plane and point "B" Screenshot (15).png
Point "B" is negative and distance between plane and point is negative (below the plane)
![image](https://github.com/user-attachments/assets/614440bd-b047-41dd-a507-5f4a9d02028f)
In above eqaution point is negative and distance is negative .So negative negative become positve
![image](https://github.com/user-attachments/assets/d5f336db-82c4-40e8-8528-cdd52ddb112d)
The product of this multiplication will always greater than zero i.e value will positive always that's means correctly classified

###### CASE-3

Lets calculate the distance of red point(which is above the plane) form the plane ![image](https://github.com/user-attachments/assets/f512c666-154d-4daf-b49a-7be91a0e6280)


Suppose "C" is that point And red line indicate the distance between plane and point

Now here point "C" is negative because its belong to negative class.And distance is positive because its above the plane

![image](https://github.com/user-attachments/assets/34bf26d0-8820-47d8-b2fa-2367c64ebfd6)

In above equation distance is positive and point is negactive And negative positive become negative

![image](https://github.com/user-attachments/assets/d7012f94-e341-434c-b3a5-e0fc20f24af1)

The product of this multiplication will always less than zero i.e value will negative always .That's means point is misclassified

###### CASE-4

Lets calculate the distance of green point(which is below the plane) form the plane ![image](https://github.com/user-attachments/assets/e7ca3eac-f1d0-42dd-a64c-5dd6cec5f0ec)

Suppose "D" is that point And green line indicate the distance between plane and point
Now here point "D" is positive because its belong to positive class.And distance is negative because its below the plane
![image](https://github.com/user-attachments/assets/e80ef0d1-e787-430b-85b7-ca5863ed0686)
In above equation point is positive and distance is negative.And positive negative become negative.
![image](https://github.com/user-attachments/assets/0393f26a-80e9-49f8-9434-34884e3761fe)

The product of this multiplication will always less than zero i.e value will negative always. That's means point is misclassified

#### Conclusion

cost function should be maximum
The summation of all the points along with the distance should be maximum
Because whenever its greater than zero the classification is correct
whenever value is negative it does misclassification

#### COST FUNCTION 

Yi is the distance

wT is coefficient

Xi is data point

We have to update this weigth(wT) untill and unless we get maximum of the summation

whichever weigth will give you maxuimum summation of all the points that particular line will your best line that line will linearly classify both classifications

#### What if we have outlier?



In above figure we have two classses red one(ve-) and blue one(ve+).
And a plane
consider the distance between plane and the point for both classes is 2. For negative class its -2 and for positive class its 2
consider magnitude of all point is 1.For negative class its -1 and for positive class its 1
we have one outlier in positive class which is belong to negative class i.e point "O".And the distance between plane and point "O" is 500
According to cost function we will do summation of all point

#### Summation of product of all point and distance

Now due to the impact of outlier all positive class points getting missclassified and negative class points are correctly classified.
Now this is because of outlier which is from negative class

#### Now we will change the best fit line 

This figure is same as above figure just plane(best fit line) is changed.
Consider distance between plane and points which is above the plane(positive) is like 1,2,3,4,5 for positive class and for negative -1,-2,-3,-4,-5
Consider magnitude of all point is 1.For negative class its -1 and for positive class its 1
For point "O" distanse is -2 and magnitude is -1

#### summation of product of all point and distance 

Now all positive class points getting correctly classified and 5 missclassification is there for negative class
But our cost function is postive which is greater than 0 so algorithm will select this line as a best fit line
Both lines/plane have missclassification .To resolve this problem we will use sigmoid function


#### SIGMOID FUNCTION

This fuction will scale the values of cost function in between 0 to 1
Formula* 
It will reduce the effect of outlier









