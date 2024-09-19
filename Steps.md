
  ### Setup a database on RDS
  
  * *creating and setting up the password*
  *keep remeber the password*

  ![Alt Text](images/create%20devops-db.PNG)

  * *Select the teir*
  
  ![alt text](images/select%20tirer.PNG)

  * *Connect with  EC2 check the box* 
  ![alt Text](images/coonect%20ec2.PNG)


 

  ### Setup the S3

* *Create S3*

  ![alt Text](images/create%20s3.PNG)

 *  *Turn on the static webhosting in properties in the last*

   ![alt text](images/static%20webhosting.PNG)
  
  * *index setting*
  
    ![Alt text](images/index%20permission.PNG)
  
  * *Writing the permission and bucket policy*
     
     ![alt TexT](images/bucket%20policy.PNG)


### Acessing the database

 ```
  sudo mysql -h <rds-endpoint> -u <db-username> -p
  ```
  ![ALt text](images/end%20poit.PNG) 
  
  *found on connectivity & security on RDS*

  *Now follow the steps in mention in Setting up in the repository of [3-teir application deployment](https://github.com/HermanTariq/3tier-application-deployment) skip 2 and 4 steps there in SQL setup*


### Backend 

conneting backend with RDS

*Step just configure index.js file*

 ![Alt text](images/connecitng%20rds%20database%20with%20back%20end.PNG)

for other things follow backend steps of [3-teir application deployment] to set up backend 

### Frontend 

follow frontend all steps as mention in the [3-teir application deployment](https://github.com/HermanTariq/3tier-application-deployment) .

### Uploading dist folder on S3 using CLI commands

* *download and unzip cli commands and configure AWS*
```sudo apt install unzip curl -y
curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"
curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"
unzip awscliv2.zip
sudo ./aws/install
aws configure
```
* *sync dist folder to s3 bucket*
   
   ```
    aws s3 sync ./dist s3://<bucketname> --region us-east-1
    ```

    