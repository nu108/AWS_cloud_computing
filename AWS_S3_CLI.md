# AWS S3 CLI COMMANDS


1) Create EC2 instance 
2) log in to EC2 
3) `sudo apt update` 
4) `sudo apt upgrade -y`

5)`sudo apt install python-pip -y`
This following command will install python 

6) `aws configure`- this command will prompt you to enter your access key and secret access key 

7) for region enter `eu-west-1`

8) enter: `json`

9) enter: `aws s3 ls`- this command allows you to view what buckets are already in S3 

# CREATE AN S3 BUCKET:

mb is used to make a bucket 

`aws s3 mb s3://<bucket-name> --region eu-west-1`

`aws s3 mb s3://tech254-nadia-bucket --region eu-west-1`

# UPLOAD A FILE TO S3 BUCKET:

`aws s3 cp <file-you-want-to-upload> s3://tech254-nadia-bucket`

`aws s3 cp testfile.txt s3://tech254-nadia-bucket`

# DOWNLOAD A FILE FROM THE S3 BUCKET, IT DOWNLOADS AS A FOLDER:

`aws s3 sync s3://tech254-nadia-bucket <folder-name>`

do ls to find folder 
 
# DELETE AN ITEM FROM S3 FOLDER 

`aws s3 rm s3://tech254-nadia-bucket/<file-you-want-to-delete>`

# DELETE EVERYTHING IN THE BUCKET
`aws s3 rm s3://tech254-nadia-bucket --recursive`

# DELETE A S3 BUCKET 
`aws s3 rb s3://tech254-nadia-bucket`


# USING PYTHON SCRIPTS

# Create a s3 bucket 

`# first thing is to import boto3 library
import boto3

# set up a s3 connection
s3 = boto3.client('s3')

# create a bucket in the eu-west-1 region
bucket_name = s3.create_bucket(Bucket="tech254-nadia-python-bucket", CreateBucketConfiguration={"LocationConstraint":"eu-west-1"})

# print the bucket name to confirm working script
print(bucket_name)`

# Upload to s3 bucket

`import boto3

# set up a s3 connection
s3 = boto3.client('s3')

# create a variable for the bucket
bucket_name = "tech254-nadia-python-bucket"

# Upload a file to the bucket
bucket_content = s3.upload_file("testfile.txt", bucket_name, "testfile2.txt")
print(bucket_content)`

# Download a file from a s3 bucket

`import boto3`

# s3 connection
s3 = boto3.client('s3')

# create a variable for the bucket
bucket_name = "tech254-nadia-python-bucket"

# download a file
s3.download_file(bucket_name, "testfile2.txt", "download_file.txt")
print(s3.download_file)`


# Delete a file in a s3 bucket

import boto3

s3 = boto3.client('s3')

response = s3.delete_object(Bucket="tech254-nadia-python-bucket", Key="testfile2.txt")

print(response)


# Delete S3 bucket

import boto3

s3 = boto3.resource('s3')

bucket = s3.Bucket("tech254-nadia-python-bucket")
response = bucket.delete()

print(response)