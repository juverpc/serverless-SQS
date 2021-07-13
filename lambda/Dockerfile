FROM public.ecr.aws/amazonlinux/amazonlinux:latest

RUN yum -y install aws-cli 
ARG AWS_DEFAULT_REGION
ARG AWS_CONTAINER_CREDENTIALS_RELATIVE_URI
RUN aws s3 cp s3://juver-upload-to-s3/model1/2/recommender.pickle.dat /var/www/ 
CMD ["lambda_function.lambda_handler"]
