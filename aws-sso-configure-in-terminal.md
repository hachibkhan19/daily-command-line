## How to Configure AWS SSO in terminal step1
  ```
    aws configure sso --profile <profile_name>
  ```
## How to Configure AWS SSO in terminal step1 Example
  ```
    aws configure sso --profile inneed
  ```

## How to Configure AWS SSO in terminal step2 Example
  ```
    SSO session name (Recommended): inneed (Anyname)
  ```
## How to Configure AWS SSO in terminal step3 Example
  ```
    SSO start URL [None]: https://d-9067575bae.awsapps.com/start/# (Provided URL)
  ```
## How to Configure AWS SSO in terminal step4 Example
  ```
  SSO region [None]: us-east-1 (Provided region)
  ```

## How to Configure AWS SSO in terminal step4 Example
  ```
  SSO registration scopes [sso:account:access]: (Just Enter Button)
  ```
## How to show Access List in terminal step5 Example
  ```
    aws s3 ls --profile inneed
  ```
## How to show Export in another  terminal step6 
  ```
  export AWS_PROFILE=<profile_name>
  ```
## How to show Export in another  terminal step6 Example
  ```
  export AWS_PROFILE=inneed
  ```
## How to show Export in another  terminal step6 Example
  ```
  export AWS_REGION=us-east-1
  ```
