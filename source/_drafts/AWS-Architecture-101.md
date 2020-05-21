---
title: AWS Architecture 101
tags: [ aws ]
---
# Note from Linuxacademy

## Access Management

Stages of access management

1. principle (a person or a system makes a request to another system) -> make authenticated request.
2. authentication (principle is given a challenge) - pin code or password, API key.
3. identity (objects that allowed to access the resources) 
4. authorization (decide if the principle able to access to resources)

Shared Responsibility Model

1. In the cloud  ( admin in charge)
2. Out of the cloud  (aws takes care)

AWS responsibility:
* software
* compute + storage + database + network
* hardware/aws global infra
* regions + availability + edge location

Inside the cloud:
* customer data
* platform
* operation System + network and firewall configuration
* encryption
* network Protection

## AWS and SA Fundamentals (Service Models)
* Iaas (Infrastructure as Service) - EC2 - (data + application + runtime + OS)
* Paas (Platform as Service) - (Virtualization + Host/Server + Network and Storage + Data Center)
* Saas (Software as Service)





