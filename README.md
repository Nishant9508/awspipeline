# DevOps Pipeline
This pipeline is created with the help of AWS, Jenkins, Git, Github and Docker. 
It's purpose is to build, stage and deploy the changes in the server whenever they are pushed into Github repository.

How it works?
- Developer commits his code in his local git reposiory and pushes it into central repository which triggers the Jenkins. 
- Jenkins runs the first build "git-job" which copies the repository items to the staging instance and uses docker to build the image out of dockerfile which was already pushed into the central repository.
- Jenkins runs the second build "build website" which executes the commands which have already been specified. The commands create a custom image from Dockerfile using Docker and then host the website on the apache server.
- After the site has been checked , Jenkins runs third build which is "pushprod" , which copies all the repository items from central repository to the workspace on Production instance and then hosts the website on its Ip address using apache server build using Dockerfile. 
- So this whole processs become automatic saving lots of time and efforts by checking at each commit.


Working : 

- We start by creating 3 ubuntu instances in the AWS which are going to serve as master, staging and production.

![image](https://user-images.githubusercontent.com/63492805/165736868-4e2d92ab-1407-49ab-9605-0a96666f6b3f.png)


-While creating the instances we also create a new key pair which is used to login into different terminal for each instance using PuTTY.

![image](https://user-images.githubusercontent.com/63492805/165737069-e75566dc-8432-4ddf-b302-7bcdb72bfda8.png)

1
![image](https://user-images.githubusercontent.com/63492805/165738795-d239d28d-a4db-4e92-8760-00a0a013a520.png)

2
![image](https://user-images.githubusercontent.com/63492805/165738815-cbb16870-fab3-45dc-babf-a3103da4a099.png)

3
![image](https://user-images.githubusercontent.com/63492805/165738852-cfc3166a-0fbd-4227-8a6f-946de8f76008.png)


- We start by installing Jdk and Jenkins in the first/master instance using terminal which we set up using putty. For using jenkins we need to open port 8080 so we can do that by changing inbound rules in the security settings for the first instance.

![image](https://user-images.githubusercontent.com/63492805/165736943-c01169f1-5ef7-4194-a7a4-d81457bb15d1.png)


- We can now access the Jenkins by using : _ipaddress_:8080 and then install the required plugins and then setting up the account.

- We create 2 slave nodes _staging_ and _production_ using the 2 other instances which we created earlier.

![image](https://user-images.githubusercontent.com/63492805/165737287-bec0594d-197c-4c0d-8616-e58050e686cc.png)

- We make 3 items in the jenkins process which are 
  - Git-job
  - build-website
  - pushprod

![image](https://user-images.githubusercontent.com/63492805/165737145-b0608413-8632-42a2-803a-1681220c7be8.png)

- As soon as the jenkins is triggered by the code push in Github repository, it then starts building _git-job_. If it is a success then it builds _build-website_ and if that is also a success it build _pushprod_ which is its final build after which website can be seen running on the ip address of production instance.

- Commands which are predefined and executed in staging and production terminal to run images.

![image](https://user-images.githubusercontent.com/63492805/165737589-f5d7c934-9e9b-430e-88c9-53470e845f4f.png)


__END__
