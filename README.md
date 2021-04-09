# Automated-testing-and-deploying-web-server
It is an DevOps project on automation of the web server for testing the web page and deploying the web page into it.

Project outline:
1. Create container image that’s has Jenkins installed using dockerfile 

2. When we launch this image, it should automatically starts Jenkins service in the container.

3. Create a job chain of job1, job2, job3 and job4 using build pipeline plugin in Jenkins 

4. Job1 : Pull the Github repo automatically when some developers push repo to Github.

5. Job2 : By looking at the code or program file, Jenkins should automatically start the respective language interpreter install image container to deploy code ( eg. If code is of PHP, then Jenkins should start the container that has PHP already installed ).

6. Job3 : Test your app if it is working or not.

7. Job4 : if app is not working , then send email to developer with error messages.

8. Create One extra job job5 for monitor : If container where app is running. fails due to any reason then this job should automatically start the container again.

Steps for project:-
Prerequisites:

1)Docker

2)ngrok software

Creating a docker container that has jenkins installed. For that we need to create the dockerfile.

!(https://media-exp1.licdn.com/dms/image/C5612AQEf-DXSn62SpA/article-inline_image-shrink_1000_1488/0/1594456751945?e=1623283200&v=beta&t=2DGAheyT2irf2dh_Zem86fvQU_xLxOGAIPQRMCkFTts)
Building the dockerfile.

No alt text provided for this image
That's it we have created the docker container that has jenkins installed. For running the container.

docker run -dit -p 8000:8080 --name jenkins_os jenkins:v3


Here, the 8000 is the port that expose to the Base OS.

We have created the jenkins container for accessing open browser and type IP:8000

https://192.176.153.129:8000 Here,192.176.153.129 is my IP address.

For getting the InitialAdminPassword.

docker exec 54b93cb3d7c0 cat /root/.jenkins/secrets/initialAdminPassword
Type the password and login to the jenkins.

Create the build pipeline of jobs using build pipeline plugin.

Job1:

Pull the Github repo automatically when some developers push repo to Github.

No alt text provided for this image
No alt text provided for this image
No alt text provided for this image
This will automatically pull the code from github.

JOB2:

By looking at the code or program file, Jenkins should automatically start the respective language interpreter install image container to deploy code ( eg. If code is of PHP, then Jenkins should start the container that has PHP already installed )

No alt text provided for this image
No alt text provided for this image
JOB3:

Testing the app whether working or not.

No alt text provided for this image
No alt text provided for this image
JOB4:

If app is not working , then send email to developer with error messages.

No alt text provided for this image
No alt text provided for this image
This will send error message if the app is not working fine!

JOB5:

If container where app is running. fails due to any reason then this job should automatically start the container again.

No alt text provided for this image
No alt text provided for this image
This is how we can create an automated testing and deploying a code on web server.

That's it , we have successfully did it.
