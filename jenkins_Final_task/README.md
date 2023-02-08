# Final Task
![jenkins-devil](https://user-images.githubusercontent.com/103090890/217597641-5a1f58b3-fcad-48d6-affa-69dcaba6a26b.png)




## 1- configure jenkins image to run docker commands on your host docker daemon

 - Dockerfile is included in the repo 
 - use the following volume to use the host daemon
``` bash
-v /var/run/docker.sock:/var/run/docker.sock
```


![Screenshot from 2023-02-05 00-06-54](https://user-images.githubusercontent.com/103090890/217598643-f6b257ab-f347-4d63-bea6-eae08932cb9e.png)


-------------------------------------------

## 2- create CI/CD for this repo https://github.com/mahmoud254/jenkins_nodejs_example.git


![Screenshot from 2023-02-05 04-35-14](https://user-images.githubusercontent.com/103090890/217598511-9877b33e-e405-4725-b630-6ae8b8b61283.png)

![Screenshot from 2023-02-05 04-36-16](https://user-images.githubusercontent.com/103090890/217598676-c1f7041e-d3c8-4c68-b481-fc84bbb624fe.png)

![Screenshot from 2023-02-05 04-43-53](https://user-images.githubusercontent.com/103090890/217598718-884b4088-fdcc-488d-a82b-e49041149cab.png)


------------------------------------------------

## 3- create docker file to build image for jenkins slave
## 4- create container from this image and configure ssh 
## 5- from jenkins master create new node with the slave container

- Slave Dockerfile is included in the repo
- Configure SSH and generate keys in master container
``` bash
ssh-keygen -t rsa
```
- Then copy the public key to ***authorized_keys*** file in ***.ssh***
- Copy the private key to jenkins credentials
- Then configure Jenkins Node

![Screenshot from 2023-02-05 07-03-17](https://user-images.githubusercontent.com/103090890/217599366-41a461ff-db31-4f6e-8b59-969e842ae44d.png)

- In the Script specify the slave agent 
```
agent { node { label 'slave' } }
```

![Screenshot from 2023-02-08 01-41-59](https://user-images.githubusercontent.com/103090890/217599903-3f88155f-e25a-442a-8d01-285cb0ed2256.png)


--------------------


## 6- integrate slack with jenkins

- Login to slack and create a channel
- Install slack plugin in Jenkins then configure Credentials and specify channel 
![Screenshot from 2023-02-08 02-26-52](https://user-images.githubusercontent.com/103090890/217600327-b7de103e-93c7-4a05-8bab-c5044b5c3065.png)


![Screenshot from 2023-02-08 02-27-39](https://user-images.githubusercontent.com/103090890/217600365-0c7cb6a9-d185-4442-845a-f2f77da93fa2.png)







-----------------------------

## 7- send slack message when stage in your pipeline is successful

- In Post actions specify Slack Notifications 

![Screenshot from 2023-02-08 02-29-08](https://user-images.githubusercontent.com/103090890/217600595-1ebdbda0-0e0c-4c11-8067-c96cb902b8b4.png)


![Screenshot from 2023-02-08 02-27-54](https://user-images.githubusercontent.com/103090890/217600537-0be3c067-016e-4de1-b2b5-e8ec481eba0a.png)

--------------------------

## 8- install audit logs plugin and test it

![Screenshot from 2023-02-08 02-32-29](https://user-images.githubusercontent.com/103090890/217600712-5a86440c-1dcc-478a-bd46-a9d735866439.png)

--------------------------------

## 9- fork the following repo https://github.com/mahmoud254/Booster_CI_CD_Project and add dockerfile to run this django app and use github actions to build the docker image and push it to your dockerhub

- The Dockerfile for this application is included in this repo called ***Dockerfile***
- Configure GitHub actions credentials to add my DockerHub credentials

![Screenshot from 2023-02-08 16-34-45](https://user-images.githubusercontent.com/103090890/217601485-632f329e-0d54-4899-8838-39e3d1d755ef.png)
![Screenshot from 2023-02-08 16-40-26](https://user-images.githubusercontent.com/103090890/217601516-5f99525a-c5bb-447a-b6de-9ea785bca3e2.png)

---------------------------------------------------

## 10- Create infrastructure pipeline to run terraform with jenkins

- The Pipeline Script is included inside this repo
- Install Terraform Plugin
- Make sure you include installation of Terraform inside the Dockerfile of Container or inside the script
- Automate the Process of creating infrastructure
- This pipeline destroys the infrastructure after successful build ***to avoid costs***

![Screenshot from 2023-02-08 17-01-26](https://user-images.githubusercontent.com/103090890/217601944-8b1e2e46-e906-4e83-9bef-904acf5c83bf.png)

![Screenshot from 2023-02-08 17-02-43](https://user-images.githubusercontent.com/103090890/217601991-3cabd85e-fe38-4baf-a337-419bd12687a4.png)



![Screenshot from 2023-02-08 17-41-44](https://user-images.githubusercontent.com/103090890/217602032-896ff044-4798-48c4-866d-8d08f984b203.png)


# Thank You !!




