FROM public.ecr.aws/amazonlinux/amazonlinux:latest

RUN yum -y install aws-cli 
ARG AWS_DEFAULT_REGION
ARG AWS_CONTAINER_CREDENTIALS_RELATIVE_URI
RUN cat /v2/credentials/d29b78e5-682f-4a15-8657-929895c78b9e
RUN aws s3 cp s3://juver-upload-to-s3/model1/2/recommender.pickle.dat /var/www/ 
CMD ["lambda_function.lambda_handler"]
