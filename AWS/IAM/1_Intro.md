# Introduction

IAM: AWS Identity and Access Management.

## Root User
One account has one root user. 

It uses email as username and a password as credentail.

## User
One account has many users. 

User can be a real person in your team or an application needs to access your AWS resources.

## Policy
A policy is an object in AWS that, when associated with an identity or resource, defines their permissions.
Permissions in the policies determine whether the request is allowed or denied. 

Most policies are stored in AWS as JSON documents.

## Groups
Individual users still have their own credentials, 
but all the users in a group have the permissions that are attached to the group.

The users' permissions are calculated based on the combination of policies.

## Role
An IAM role is similar to an IAM user, 
in that it is an AWS identity with permission policies that determine what the identity can and cannot do in AWS. 

However, instead of being uniquely associated with one person, a role is intended to be assumable by anyone who needs it.

For example, you might want to grant users in your AWS account access to resources they don't usually have, 
or grant users in one AWS account access to resources in another account. 
