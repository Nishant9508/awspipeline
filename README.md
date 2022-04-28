# awspipeline
This pipeline is created with the help of AWS, Jenkins, git, github and docker. 
It's purpose is to build, test and deploy the changes in the server whenver they are pushed into github repository.

We start by creating 3 ubuntu instances in the AWS which are going to serve as master, testing and production.

![image](https://user-images.githubusercontent.com/63492805/165736868-4e2d92ab-1407-49ab-9605-0a96666f6b3f.png)

While creating the instances we also create a new key pair which is used to login into different terminal for each instance using PuTTY.
![image](https://user-images.githubusercontent.com/63492805/165737069-e75566dc-8432-4ddf-b302-7bcdb72bfda8.png)


![image](https://user-images.githubusercontent.com/63492805/165736943-c01169f1-5ef7-4194-a7a4-d81457bb15d1.png)
![image](https://user-images.githubusercontent.com/63492805/165737145-b0608413-8632-42a2-803a-1681220c7be8.png)
![image](https://user-images.githubusercontent.com/63492805/165737287-bec0594d-197c-4c0d-8616-e58050e686cc.png)
![image](https://user-images.githubusercontent.com/63492805/165737589-f5d7c934-9e9b-430e-88c9-53470e845f4f.png)
![image](https://user-images.githubusercontent.com/63492805/165738795-d239d28d-a4db-4e92-8760-00a0a013a520.png)
![image](https://user-images.githubusercontent.com/63492805/165738815-cbb16870-fab3-45dc-babf-a3103da4a099.png)
![image](https://user-images.githubusercontent.com/63492805/165738852-cfc3166a-0fbd-4227-8a6f-946de8f76008.png)
