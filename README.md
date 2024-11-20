apt-get update && apt-get install awscli s3fs -y

Run aws configure and add credentials from the s3fs_user

Add credentials from s3fs_user in $HOME/.passwd_s3fs: echo access_key:secret_access_key > $HOME/.passwd_s3fs

chmod 600 $HOME/.passwd_s3fs

Run command to mount andrei-bucket-12345 in /home/ubuntu/andrei-bucket:

s3fs andrei-bucket-12345 /home/ubuntu/andrei-bucket -o url=https://s3-eu-west-1.amazonaws.com -o passwd_file=${HOME}/.passwd_s3fs