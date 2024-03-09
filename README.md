# Digital CSA Americas Azure Bootcamp - Lab2 - Azure Front Door 

## Introduction

The Internet is much like water, in one hand an amazing thing that provides life/capability for so much, but in the other hand can be the most destructive force in nature.  Large numbers of users, large size and/or number of resources on pages, malicious activity, site slows down the further away it is, or events triggering massive spikes in traffic are only a few of the problems **Azure Front Door** addresses.  This challenge based hack is intended to teach you how to evolve a simulated local web site (https://www.contosomask.com) into a globally accelerated, protected web site with burst offset.

## Learning Objectives
In this hack you will be solving the common problem that websites have with the Front Door services from Azure:

1. Provision an Azure Front Door and set up SSL
2. Provision and Configure Web Application Firewall (WAF)
3. Configure simple/complex routing rules
4. Discover and Monitor traffic and WAF insights thru Log Analytics

## Challenges
1. [Setup your Environment and Discover](Student/Challenge01.md)
   - Create Azure resources and leverage your Browser's Dev Tools to analyze the Website
2. [Provision your Front Door](Student/Challenge02.md)
   - Create a Front Door account with custom DNS and SSL
3. [Provision a Web Application Firewall (WAF)](Student/Challenge03.md)
   - Create a Web Application Firewall Policy and guard your site!
4. [Force HTTPS thru Rules Engine](Student/Challenge05.md)
   - Create routing rule to force all traffic to HTTPS.  
5. [Monitor WAF traffic thru Log Analytics](Student/Challenge06.md) [ Optional ]
   - Use ZAP tool to trigger OWASP and High Risk traffic and monitor WAF logs

## Prerequisites
- Your own Azure subscription with Owner access
  - Or a Resource Group with Contributor access and ability to manage [Resource Providers](https://docs.microsoft.com/en-us/azure/azure-resource-manager/management/resource-providers-and-types)
- Install [ZAP](https://www.zaproxy.org/download/) [ Required for Challenge#5 ]
- Some form of Chromium Web Browser installed
  - [Microsoft Edge](https://www.microsoft.com/en-us/edge)
  - [Google Chrome](https://www.google.com/chrome/)

