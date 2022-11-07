## Steps for training MNIST AI model and generation of AI model artifacts

- Open the MNIST_AI_MODEL.ipynb notebook in google colab or use Vscode editor or OCI data science project console.
- Use shift + enter keyboard key to run indivisual notebook code cell.
- OCI Object storage provides an Amazon S3 compatible API and Amazon’s Python SDK which is also called BOTO3.
- To use Boto3, you must first import it and indicate which service or services you're going to use:
import boto3
s3 = boto3.resource(
 's3',
 region_name="us-phoenix-1",
 aws_secret_access_key="YOUR SECRET KEY=",
 aws_access_key_id="YOUR ACCESS KEY",
 endpoint_url="https://axutkjfnpof3.compat.objectstorage.us-phoenix-1.oraclecloud.com"
)


- To upload the files to the Oracle bucket, use the upload_file method. The upload_file method accepts a file name, a bucket name, and an object name. The method handles large files by splitting them into smaller chunks and uploading each chunk in parallel. BTA project has used the following function to upload the file into the bucket.

s3.meta.client.upload_file(file_name, bucket, object_name)

