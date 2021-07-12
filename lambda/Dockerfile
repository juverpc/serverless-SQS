FROM public.ecr.aws/lambda/python:3.6
RUN yum update -y

# Working directory
WORKDIR /var/task/

# Move the script into the workdir
COPY . /var/task/
RUN aws s3 cp s3://juver-upload-to-s3/model1/1/Métodos 2da parte.zip /var/task/ --recursive
RUN ls -a

# Install all the dependencies
RUN pip3 install --upgrade pip
RUN pip3 install --no-cache-dir -r requirements.txt

CMD ["lambda_function.lambda_handler"]
