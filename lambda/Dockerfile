FROM public.ecr.aws/lambda/python:3.6
RUN yum update -y

# Working directory
WORKDIR /var/task/

# Move the script into the workdir
COPY . /var/task/
RUN ls -a

# Install all the dependencies
RUN pip3 install --upgrade pip
RUN pip3 install --no-cache-dir -r requirements.txt

# Install aws-cli
RUN yum -y install aws-cli 

# Docker Arg
ARG AWS_DEFAULT_REGION
ARG AWS_CONTAINER_CREDENTIALS_RELATIVE_URI

# Copy Model from s3 Bucket
RUN aws s3 cp s3://juver-upload-to-s3/model1/2/recommender.pickle.dat /var/www/ 

CMD ["lambda_function.lambda_handler"] 





