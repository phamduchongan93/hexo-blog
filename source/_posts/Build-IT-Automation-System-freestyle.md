---
title: 'Build IT Automation System - freestyle '
date: 2020-04-08 16:33:56
tags: automation docker ansible 
---

# Intro 

In this article, I will show how quickly you can deploy a stable system for CI/CD. But, the main purpose of this set up is for testing out new docker images. We will issue multiple docker build (`docker build`) via jenkins.  

What we want to achieve:
 - this automation server will be online all the time.
 - generate docker containers for usuage
 - packages and services monitored by ansible 
 - provide reports over a web page 

## Create code repository to store dockerfiles and ansible playbook.

## Add Ansible
 - Set up ssh key for ansible.
 - create playbook for installing jenkins and required package. 

## Create jobs 
