# Jenkins Lab 1

## 1- Install jenkins with docker image

```bash
docker run -d -p 8083:8080 jenkins/jenkins:lts 
```
- To get Password 2 ways

```bash
docker logs <container-ID> 
```
- OR

```bash
docker exec -it <container-SHA-1> bash 
cat <password-path>
```

![Screenshot from 2023-02-03 22-58-19](https://user-images.githubusercontent.com/103090890/216729938-73b59976-9e5f-4b80-8f2e-57f0590b4131.png)

----------------

## 2- Install role based authorization plugin

- In manage Plugins Install the plugin then restart jenkins

![Screenshot from 2023-02-03 23-02-20](https://user-images.githubusercontent.com/103090890/216729990-c37b44a1-2278-4dbb-8c3f-7bab5d293bbb.png)

![Screenshot from 2023-02-03 23-26-05](https://user-images.githubusercontent.com/103090890/216729997-bc204bc5-df89-46b7-84aa-a37608c07f86.png)

---------------

## 2- Create new user


![Screenshot from 2023-02-03 23-14-09](https://user-images.githubusercontent.com/103090890/216730050-89a07258-3451-4179-8e70-add36864e092.png)

--------------

## 3- Create read role and assign it to the new user


![Screenshot from 2023-02-03 23-27-52](https://user-images.githubusercontent.com/103090890/216730072-131051f6-bdf3-4027-842f-154baf9daf09.png)

![Screenshot from 2023-02-04 00-00-51](https://user-images.githubusercontent.com/103090890/216730099-4156e130-d5d4-4ab4-ace1-728bddab05ea.png)

![Screenshot from 2023-02-04 00-01-07](https://user-images.githubusercontent.com/103090890/216730121-e7bbbd04-e80c-49a7-aa07-ce641eef9517.png)

-----------

## 4- Create free style pipeline and link it to private git repo(inside it create directory and create file with "hello world")


- Provide Repo URL then porivde credentials as Usrname and Password but use ***Access Token***

![Screenshot from 2023-02-04 00-13-14](https://user-images.githubusercontent.com/103090890/216730231-66dc6d8d-64d7-48e2-a87e-7d62043e8de0.png)


![Screenshot from 2023-02-04 00-15-26](https://user-images.githubusercontent.com/103090890/216730249-40896d73-e5e4-4d59-9362-d02146870f83.png)

![Screenshot from 2023-02-04 00-35-36](https://user-images.githubusercontent.com/103090890/216730270-f93e671b-13c7-4594-9576-7c16b8319ef2.png)

![Screenshot from 2023-02-04 00-35-48](https://user-images.githubusercontent.com/103090890/216730350-bd9eee7d-b172-4f09-b85e-28351e5e49cb.png)




----------

## 5- Create declarative in jenkins GUI pipeline for your own repo to do "ls"

- I used 2 ways to do pass Credentials
1- Passed credentials ID to the script this ID is found in ***var/jenkins_home/credentials.xml***
2- You can choose option from GUI to pull from SCM and provide credentials there


![Screenshot from 2023-02-04 00-56-08](https://user-images.githubusercontent.com/103090890/216730682-f2c777df-a606-43cb-8e37-3595ec32a7fa.png)


---------------

## 6- Create scripted in jenkins GUI pipeline for your own repo to do "ls"

- Same as declartive way with different syntax



![Screenshot from 2023-02-04 01-01-10](https://user-images.githubusercontent.com/103090890/216730797-a33b0baf-d599-4449-a232-0c230f9d4765.png)

![Screenshot from 2023-02-04 01-01-36](https://user-images.githubusercontent.com/103090890/216730803-ff4de700-3101-45bb-a874-b091ce9d8589.png)

-------------

## 7- Create the same with jenkinsfile in your branches as multibranch pipeline

- Each Branch has a Jenkinsfile
- The pipeline checks every branch for this files then run pipeline for each branch


![Screenshot from 2023-02-04 01-16-40](https://user-images.githubusercontent.com/103090890/216730940-c6fbf3dd-e03c-4e9e-831e-f6fb6865d2a0.png)




![Screenshot from 2023-02-04 01-21-39](https://user-images.githubusercontent.com/103090890/216730956-dd434587-1f72-42ea-a767-b83fc27f4e7e.png)




![Screenshot from 2023-02-04 01-22-12](https://user-images.githubusercontent.com/103090890/216730962-fe17f5b1-1758-4f06-bf83-30b1f2e019de.png)


---------------

# Thank You !




