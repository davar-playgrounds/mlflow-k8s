FROM python:3.7.7-slim

RUN pip install boto3==1.12.31 mlflow==1.7.2 pymysql==0.9.3 && cryptography==2.9

EXPOSE 5000

CMD mlflow server \
    --backend-store-uri mysql+pymysql://root:${MYSQL_ROOT_PASSWORD}@mysql-service/${MYSQL_DATABASE} \
    --default-artifact-root s3://${S3_BUCKET}/mlflow-artifacts \
    --host 0.0.0.0
