# Environment Variables<a name="cli-configure-envvars"></a>

Environment variables provide another way to specify configuration options and credentials and can be useful for scripting or temporarily setting a named profile as the default\.

**Important**  
Setting one of the following environment variables overrides all other ways of specifying that option *except* specifying the option as a command line parameter\.

The AWS CLI supports the following environment variables:
+ `AWS_ACCESS_KEY_ID` – Specifies an AWS access key associated with anIAM user or role\.
+ `AWS_SECRET_ACCESS_KEY` – Specifies the secret key associated with the access key\. This is essentially the 'password' for the access key\.
+ `AWS_SESSION_TOKEN` – Specifies the session token value that is required if you are using temporary security credentials\. For more information, see the [Output section of the assume\-role command](https://docs.aws.amazon.com/cli/latest/reference/sts/assume-role.html#output) in the *AWS CLI Command Reference*\.
+ `AWS_DEFAULT_REGION` – Specifies the [AWS region](cli-chap-configure.md#cli-quick-configuration-region) to send the request to\.
+ `AWS_DEFAULT_OUTPUT` – Specifies the output format to use\.
+ `AWS_PROFILE` – Specifies the name of the [CLI profile](cli-configure-profiles.md) with the credentials and options to use\. This can be the name of a profile stored in a `credentials` or `config` file, or the value `default` to use the default profile\.
+ `AWS_CA_BUNDLE` – Specifies the path to a certificate bundle to use for HTTPS certificate validation\.
+ `AWS_SHARED_CREDENTIALS_FILE` – Specifies the location of the file that the AWS CLI uses to store access keys \(the default is `~/.aws/credentials`\)\.
+ `AWS_CONFIG_FILE` – Specifies the location of the file that the AWS CLI uses to store configuration profiles \(the default is `~/.aws/config`\)\.

The following example shows how you could configure environment variables for the default user\. These values would override any values found in a named profile, or instance metadata\. Once set, these values can be overridden by specifying a parameter on the CLI command line, or by changing or removing the environment variable\. 

**Linux, macOS, or Unix**

```
$ export AWS_ACCESS_KEY_ID=AKIAIOSFODNN7EXAMPLE
$ export AWS_SECRET_ACCESS_KEY=wJalrXUtnFEMI/K7MDENG/bPxRfiCYEXAMPLEKEY
$ export AWS_DEFAULT_REGION=us-west-2
```

**Windows**

```
C:\> set AWS_ACCESS_KEY_ID=AKIAIOSFODNN7EXAMPLE
C:\> set AWS_SECRET_ACCESS_KEY=wJalrXUtnFEMI/K7MDENG/bPxRfiCYEXAMPLEKEY
C:\> set AWS_DEFAULT_REGION=us-west-2
```