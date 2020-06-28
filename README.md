# s3-file-upload

### Create a policy `s3-file-upload-policy`
```
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "VisualEditor0",
            "Effect": "Allow",
            "Action": [
                "s3:PutObject",
                "s3:GetObject",
                "s3:ListBucket"
            ],
            "Resource": [
                "arn:aws:s3:::arn:aws:s3:::<bucket-name>/*",
                "arn:aws:s3:::arn:aws:s3:::<bucket-name>"
            ]
        }
    ]
}
```

### Attach policy to EC2 / ElasticBeanstalk Instance that generates the presigned url or file-upload.
```
- Go to IAM - 
- Click on the Role currently associated with EC2 /ElasticBeanstalk.
- Click on 'Add Inline Policy'
- Attach the `s3-file-upload-policy` to the role.
- Click on `Import managed polciy`
- Filter polices -> Customer managed
- Check the policy -> Click on Import
```
