# juicesync

Juicesync is a tool to move your data in object storage between any clouds or regions.

# How it works?

juicesync will scan all the keys from two object stores, and comparing them in ascending order to find out missing or outdated keys, then download them from the source and upload them to the destination in parallel.

# Install

After installed Go-1.9+

```
go get github.com/juicedata/juicesync
$HOME/go/bin/juicesync
```

# Usage

```
juicesync [options] SRC DST
```

SRC and DST must be an URI of the following object storage:

- file: local files
- s3: Amazon S3
- gcs: Google Cloud Storage
- wasb: Windows Azure Blob Storage
- oss: Aliyun OSS
- cos: Tencent Cloud COS
- ks3: KSYun KS3
- ufile: UCloud UFile
- qingstor: Qingcloud QingStor
- bos: Baidu Cloud Object Storage
- jss: JCloud Object Storage
- qiniu: Qiniu
- b2: Backblaze B2
- space: Digital Ocean Space

SRC and DST should be in the following format:

NAME://[ACCESS_KEY:SECRET_KEY]BUCKET.ENDPOINT[/PREFIX]

Some examples:

- file://Users/me/code/
- s3://my-bucket.us-east1.amazonaws.com/
- s3://access-key:secret-key-id@my-bucket.us-west2.s3.amazonaws.com/prefix
- gcs://my-bucket.us-west1.googleapi.com/
- oss://test.oss-us-west-1.aliyuncs.com
- cos://test-1234.cos.ap-beijing.myqcloud.com

Note:

- S3: The access key and secret key for S3 could be provided by AWS_ACCESS_KEY_ID and AWS_SECRET_ACCESS_KEY, or IAM role.
- COS: The AppID should be part of the bucket name.
- GCS: The machine should be authorized to access Google Cloud Storage.
