# Automate Terraform with GitHub Actions


This repo is a companion repo to the [Automate Terraform with GitHub Actions](https://learn.hashicorp.com/tutorials/terraform/github-actions?in=terraform/automation).

This entire tutorial is performed by referring Hashicorp's article highlighted above.

Some key points to note:  
a) The version provided in the article is 0.13 which didn't work in my case.  
Since my local machine had a version of 1.0.0; I replaced the same in the .yml file  
  
b) I ran into the issue of not being able to connect to Terraform Cloud from Github inspite of updating the correct API token.  
So after multiple retries; I found that I have to manually run the "terraform login" command on my local command line and make sure that I create a new token which is updated correctly in the "credentials.tfrc.json" file locally. Then update this same token within TF_API_TOKEN on github secrets.  
  
If you see the below error:  
  
 " The "remote" backend encountered an unexpected error while reading the organization settings: unauthorized"; please follow the instructions in point b  
   
c) The way this tutorial works is:  
   A developer would create a pull request for the master branch ==> Terraform would create a plan for the resources to be provisioned ==> Then the code reviewer can go through those changes and see if the plan is correct ==> Once they merge the pull request manually; then terraform would apply those plan changes and provision AWS resources  

