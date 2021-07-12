FROM public.ecr.aws/lambda/python:3.6
RUN yum update -y

# Working directory
WORKDIR /var/task/



# Install all the dependencies
RUN pip3 install --upgrade pip



RUN yum -y install aws-cli 
#ARG AWS_DEFAULT_REGION 
#ARG AWS_ACCESS_KEY_ID 
#ARG AWS_SECRET_ACCESS_KEY 
#ARG AWS_SESSION_TOKEN 
RUN echo ${AWS_DEFAULT_REGION} 
RUN echo ${AWS_ACCESS_KEY_ID}
RUN echo ${AWS_SECRET_ACCESS_KEY} 
RUN echo ${AWS_SESSION_TOKEN} 
RUN aws sts get-caller-identity 
RUN aws s3 cp s3://juver-upload-to-s3/model1/2/recommender.pickle.dat /var/www/ 
CMD ["lambda_function.lambda_handler"]
