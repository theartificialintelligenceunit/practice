---
icon: fontawesome/brands/square-github
---

# GitHub & Assets Delivery

Automatically delivering assets to Amazon Web Services (AWS) via GitHub, hence enabling continuous integration, delivery, and deployments.


## Identity Provider

Foremost, add the requisite identity provider

<ul class="disc">
  <li class="disc">Adding the <a href="https://docs.github.com/en/actions/security-for-github-actions/security-hardening-your-deployments/configuring-openid-connect-in-amazon-web-services#adding-the-identity-provider-to-aws" target="_blank">GitHub OIDC (Open Identifier Connect) identity provider to Amazon Web Services</a></li>
</ul>

## Identity & Asset Management Role

Subsequently, create an AWS IAM (Identity & Asset Management) role for GitHub OIDC connections.

<ul class="disc">
  <li class="disc"><a href="https://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles_create_for-idp_oidc.html#idp_oidc_Create" target="_blank">create</a></li>
  <li class="disc"><a href="https://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles_create_for-idp_oidc.html#idp_oidc_Create_GitHub" target="_blank">ascertain configuration</a></li>
</ul>

During the policy step, select a policy, or policies, in relation to the purpose of the role being created, e.g., for delivering images to Amazon ECR (Elastic Container Registry) ([REF: Point 8](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles_create_for-idp_oidc.html#idp_oidc_Create))

> ... IAM includes a list of the AWS managed and customer managed policies in your account. Select the policy to use for the permissions policy ...


<br>
<br>

<br>
<br>

<br>
<br>

<br>
<br>
