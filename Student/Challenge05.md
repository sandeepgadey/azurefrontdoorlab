# Challenge 4 - Force HTTPS thru Rules Engine

[< Previous Challenge [3]](./Challenge03.md)&nbsp;&nbsp;-&nbsp;&nbsp;**[Home](../README.md)**&nbsp;&nbsp;-&nbsp;&nbsp;[Next Challenge [5] >](./Challenge06.md)

## Introduction

We now have a globally scaled website, protected by WAF. Now we have to make sure that all traffic is forced to HTTPS.  

We can use the new [Rules Engine in Front Door](https://docs.microsoft.com/en-us/azure/frontdoor/front-door-rules-engine) to specify rules to execute at the edge before sending traffic to your origin.  

## Description

For this challenge we are going to:
1. Create a Rules Engine for Front Door and associate to all Routing rules
2. Create a rule that redirects HTTP to HTTPS and it must support any HTTP request that comes in as outlined [here](https://learn.microsoft.com/en-us/azure/frontdoor/front-door-how-to-redirect-https)

## Success Criteria

- Demonstrate the website still works thru Front Door via http://frontdoor.***SITENAME***.contosocsalabs.com redirects to https://frontdoor.***SITENAME***.contosocsalabs.com.  Also verify that deeper links also redirects to HTTPS version.

## Learning Resources

- [Azure Front Door Rules Engine Matching Criteria](https://docs.microsoft.com/en-us/azure/frontdoor/front-door-rules-engine-match-conditions)
- [Azure Front Door Rules Engine Actions](https://docs.microsoft.com/en-us/azure/frontdoor/front-door-rules-engine-actions)

