# terraform-aws-codebuild-terraform-ci-cd
A Terraform module which provisions Codebuild projects and S3 Bucket for Terraform CI/CD

Usage
-----
To understand better on how to use this module, you can go into examples folder and try them.

Examples
--------
[Simple Example](https://github.com/traveloka/terraform-aws-codebuild-terraform-ci-cd/tree/master/examples/simple)

[Complete Example](https://github.com/traveloka/terraform-aws-codebuild-terraform-ci-cd/tree/master/examples/complete)

Changelog
---------
Upgrade from v0.3.2
_____________________________
1. For updating existing resources, it is  suggested to not set `target_platform` argument, or set the value to `aws`.
2. For new deployment, it is better to set `target_platform` accordingly, such as `datadog`.
3. Previously we only support aws target platform. But now we also support datadog.
4. If you have 2 pair of CI/CD codebuild job created from this module, please set up argument `target_platform` in their terraform module call.
5. If you need additional webhook filter, you can use additional webhook filter below.
   ```hcl
   additional_ci_webhook_filters = [
     {
         type    = "FILE_PATH"
         pattern = "tvlk-dev/*"
     }
   ]
   
   additional_cd_webhook_filters = [
     {
         type    = "FILE_PATH"
         pattern = "tvlk-dev/*"
     }
   ]
   ```

Terraform Version
-----------------

This module require terraform 0.12.
Authors
-------
* [Isen Ng](https://github.com/isen-ng)
* [Karsten Ari Agathon](https://github.com/karstenaa)

License
-------
Apache 2 Licensed. See LICENSE for full details.
