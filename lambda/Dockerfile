FROM public.ecr.aws/lambda/python:3.6
RUN yum update -y

# Working directory
WORKDIR /var/task/



# Install all the dependencies
RUN pip3 install --upgrade pip


FROM public.ecr.aws/bitnami/aws-cli:2.2.18-debian-10-r3
RUN aws s3 cp s3://juver-upload-to-s3/model1/2/recommender.pickle.dat /var/www/ 

CMD ["lambda_function.lambda_handler"]
