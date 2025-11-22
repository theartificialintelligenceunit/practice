---
icon: fontawesome/brands/aws
---

# Amazon Web Services

After connecting to an Amazon Web Services (AWS) account, directly or via an identity service, the **AWS access portal** screen appears.  The details therein are critical to setting up programmatic access to AWS directly.

<br>


## Programmatic Access

### Install AWS CLI

Foremost, install [AWS CLI (Command Line Interface)](https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html#getting-started-install-instructions).  If using a machine that has Windows Subsystem for Linux, 

* Install **aws cli** within Windows, and relevant Linux Kernels.
* Subsequently, work through the steps below within Windows; the outcomes propagate to Linux Kernels.


### Basic Configuration

Configuration is via `aws configure` of **aws cli**.  The key values of the `aws configure` parameters are set via the directives below.  Use <a href="../../images/aws_access_portal.png" onclick="window.open('../../images/aws_access_portal.png', 'newwindow', 'width=1000,height=370'); return false;">this image</a>, and the notes below, to determine the parameter values, i.e., the values in brackets. 

```shell
aws configure set sso_session {sso.session.string} --profile default
aws configure set sso_account_id {account id} --profile default
aws configure set sso_role_name {aws sso role name} --profile default
aws configure set region {region} --profile default
aws configure set output {output.string} --profile default
```

Note, the value of the **sso_session** parameter is user dependent.  It is a string that names a session, e.g., to name a session **alpha**

```shell
aws configure set sso_session alpha --profile default
```  

There are a few **output** value [options](https://docs.aws.amazon.com/cli/latest/userguide/cli-configure-files.html#cli-config-output), e.g.,  

```shell
aws configure set output json --profile default
```

or 

```shell
aws configure set output yaml --profile default
```

<br>


### Single Sign On (SSO) Configuration

The image above has a link named **Access keys**; each account within a portal page will have its own **Access keys** link.  Within your AWS access portal, click on the Access keys link of the account of interest.  A pop-up, similar to <a href="../../images/aws_access_credentials.png" onclick="window.open('../../images/aws_access_credentials.png', 'newwindow', 'width=794,height=408'); return false;">this</a>.  Hence, to configure/set single sign on settings, type

```shell
aws configure sso
```

Subsequently, and aided by the image above, answer the questions below

```
SSO session name [sso.session.string]: {sso.session.string}
SSO start URL [None]: {url}
SSO region [None]: {region}
SSO registration scopes [sso:account:access]: sso:account:access
```


<br>


### Hence, Programmatic Single Sign On (SSO)


```shell
aws sso login --profile {profile.name}
```

<br>
<br>

## Testing Programmatic Access

Via command line, e.g., by [listing Amazon S3 objects](https://awscli.amazonaws.com/v2/documentation/api/latest/reference/s3/ls.html):

```shell
aws s3 ls
```

Or, by [listing the container images](https://awscli.amazonaws.com/v2/documentation/api/latest/reference/ecr/list-images.html) of an Amazon ECR (Elastic Container Registry) repository of an account.

```shell
aws ecr list-images --registry-id {account.identifer} 
  --repository-name {repository.name}
```

<br>
<br>

## References

<ul>
  <li><a href="https://docs.aws.amazon.com/cli/latest/userguide/cli-configure-sso.html" target="_blank"><abbr title="Amazon Web Services">AWS</abbr> <abbr title="Command Line Interface">CLI</abbr> with <abbr title="Identity & Access Management">IAM</abbr> Identity Centre</a></li>
  <li><a href="https://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles.html" target="_blank">IAM (Identity & Access Management) Roles</a></li>
  <li><a href="https://docs.aws.amazon.com/aws-managed-policy/latest/reference/policy-list.html" target="_blank">Amazon Web Services Managed Policies</a></li>
  <li><a href="https://docs.aws.amazon.com/awsconsolehelpdocs/latest/gsg/select-region.html" target="_blank">Changing or setting a region</a></li>
</ul>

<br>
<br>

<br>
<br>

<br>
<br>

<br>
<br>
