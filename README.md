
# Week 5 Exercises
This tutorial assignment will help you get familiar with boto3, EC2 and S3 bucket. You will also get experience performing operations on EC2 and S3 bucket using boto3.

### Set Up Instructions

#### Credential Configuration:
1. Log into your AWS account.
2. Click on your name on the top-right navigation bar, and click on **Security Credentials**.
3. Scroll to the **Access keys** section, and click **Create access key**.
4. Download the created key file on your computer. This file contains two important fields: **Access key ID** and **Secret access key**.
5. Open WriteCredentials.py. Copy and paste the values: AWSAccessKeyID = your **Access key ID**, and AWSSecretKey = your **Secret access key**.
6. Update the two **file** variables such that they point to an **.aws** folder in your root directory. 
6. Run the file:
``` $ python WriteCredentials.py ```
7. Check that the credentials were correctly written:
```$ cat ~/aws/credentials```
It should look something like (but with your own access keys):
```
[default]
aws_access_key_id=KDREUFRUSRJEREIROWQEO!DX
aws_secret_access_key=CDWQ__JXEKJKXSEW/QJKEJRUK@#$UI!@I@U#XD
```
```$ cat ~/aws/config```
It should look something like:
```
[default]
                      region = us-east-1
                      output = json
                      [profile prod]
                      region = us-east-1
                      output = json%
```


#### Subnet Configuration

In this step, you need to determine the id of your default network subnet and update the field subnet_id in the config.py file

1. In your AWS account, click on the search bar on top of the screen and type vpc. Then, click on VPC from the dropdown.
2. Click on Subnets and copy the **subnet ID** of any one of the available subnets.
3. Open config.py and paste the **subnet ID** into the subnet_id field.


#### S3 Bucket

1. In your AWS account, type S3 on the search bar. Click on S3 that is shown on the dropdown.
2. On the next page, click on Create Bucket. You might want to keep all Configure options or Set permissions as default. That is, only specify your bucket name and click next.
3. You will now find your s3 bucket in the list.


### Exercises:

- You should now be able to run this flask application the same way that you have in previous exercises. Make sure your virtual environment is active, and use ```$ flask --app main run```.
- **WARNING**: By clicking the 'new' button on the UI of this application, new EC2 instances will be created on your account. You may want to stop these instances when you are done with the exercise. 

1. Modify the function ec2_list() from ec2_exmaples.py so that it displays
information only for instances with the selected status.

- Documentation for the EC2 filter function is available [here](https://boto3.amazonaws.com/v1/documentation/api/latest/reference/services/ec2.html). Search for the phrase
ec2.instances.filter and you will be directed to the relevant section.
- The filter function takes a very large number of parameters. The parameter that
reflects the status of the instance is called instance-state-name.

2. Finish writing the function s3_delete() in file s3_examples.py so that you can delete any object from an S3 bucket.

- Documentation for S3 is available [here](https://boto3.amazonaws.com/v1/documentation/api/latest/reference/services/s3.html#S3.Client.delete_object). Search for the phrase client.delete_object and you will be directed to the relevant section.
- **Note**: if you are having trouble with the **Choose File** button, try dragging an image into the webpage instead.



