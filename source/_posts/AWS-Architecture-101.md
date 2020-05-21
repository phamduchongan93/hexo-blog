---
title: AWS Architecture 101
tags:
  - aws
date: 2020-05-21 08:05:39
---

# Note from Linuxacademy


## Create an AWS Account, AWS Free Tier, Usage Tracking, and Biling Widget 

* Create Billing Alarm
* Utilizing for 

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
* IaaS (Infrastructure as Service) - EC2 - (data + application + runtime(python and javascript) + OS)
* PaaS (Platform as Service) - (Virtualization + Host/Server + Network and Storage + Data Center)
* SaaS (Software as Service) - email products and serivices, office365 and G suit.

## Hight Availability and Fault Tolerance 
* Fault Tolerance (FT): doesn't affect end user (using load balancer to resolve the issues.
* High AVailability (HA): software configuration  to recover in a case of failure. (spinning up another instance)

## Disaster Recovery
* Recovery Point Object (RPO) - 
  - Related to back up operation
    Example: invertal of backup. Backing up hourly or backing up daily. 1 hour RPO is better than 1 day RPO, but will cost more. 

* Recovery Time Objective (RTO) - How long does it to take to recover the service?  the shorter time to recover will cost more. 

## Scaling
* There are two type of scaling 
  - Vertical Scaling: increase the instace, increasing CPU and Memory. There is a limitation of capacity of scaling on the instance. 
  - Hortizontal Scaling: add another instnces, scaling to infinitively. Using small size instance will save the cost. This scaling need the application support.

## Tiered Application Design
* There are 3 tier in Application Design: Presentation + Logic + Data:
  - Presentation: interact with consumer of the application.
  - logic tier: deliver application functionality. 
  - data tier: control interaction with database.
Theese isolated tier can be developed with horitzontal. For example, one or two instances can hanble presentation.

