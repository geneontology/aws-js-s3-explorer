# AWS JavaScript S3 Explorer

This is a fork of lpalbou/aws-js-s3-explorer, from the the upstream [AWS S3 Explorer](https://github.com/awslabs/aws-js-s3-explorer).

## HOWTO

To work against different buckets, one must first update index.html to point to the correct bucket:
```diff
- s3exp_config.Bucket = "geneontology-reroute"
+ s3exp_config.Bucket = "go-data-product-release"
```

With the same (updated) bucket, reindexing looks like: 
`you@computer:~/local/src/git/aws-js-s3-explorer[master]$:) AWS_ACCESS_KEY_ID=123 AWS_SECRET_ACCESS_KEY=456 time python3 s3_add_index.py -o go-data-product-release`

Afterwards, you may want to run your invalidations on CloudFront, if that is what you are using.

## Notes

Currently, there is no way to do a partial update--the entire repo is reindexed with this action.
