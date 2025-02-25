# Use AWS Lambda Python 3.11 with explicit architecture
FROM public.ecr.aws/lambda/python:3.11



# Install system dependencies
RUN yum update -y && \
    yum install -y gcc gcc-c++ make && \
    yum clean all

# Install Python dependencies
COPY requirements.txt .
RUN pip install --upgrade pip && \
    pip install -r requirements.txt

# Copy application source code
COPY src/ ${LAMBDA_TASK_ROOT}/app/

# Set proper Lambda handler command
CMD ["app.app.handler"]