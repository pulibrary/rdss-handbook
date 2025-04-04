1. [Login to aws](https://princeton.edu/aws)
1. Connect with the [AWS West S3](https://us-west-1.console.aws.amazon.com/s3/buckets?bucketType=general&region=us-west-1)
1. Create the bucket 
   1. Click on Create Bucket
   1. Fill in the bucket name with `pdc-describe-staging-embargo-preservation`, `pdc-describe-production-embargo-preservation`, `pdc-describe-staging-preservation`, or `pdc-describe-staging-preservation`
   1. Click on `Enable` under `Bucket Versioning`
   1. Click on `Create Bucket`
   1. Click on the newly created bucket
1. Configure the bucket to Delete old versions
   1. click `Management` tab
   1. click on `Create lifecycle rule`
   1. Fill in `Remove old deleted versions` for the name
   1. choose `Apply to all objects in the bucket`
   1. check `I acknowledge...`
   1. check `Permanently delete noncurrent versions of objects`
   1. check `Delete expired object delete markers or incomplete multipart uploads`
   1. Fill in 30 (14 for deposit) in `Days after objects become noncurrent`
   1. check `Delete expired object delete markers`
   1. check `Delete incomplete multipart uploads`
   1. Fill in 14 in `Number of days`
   1. Click on `Create Rule` 
1. Configure the Preservation copy from the S3 to Presrvation bucket
