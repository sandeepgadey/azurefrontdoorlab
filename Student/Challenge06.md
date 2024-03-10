# Challenge 4 - Monitor WAF traffic thru Log Analytics

[< Previous Challenge [4]](./Challenge05.md)&nbsp;&nbsp;-&nbsp;&nbsp;**[Home](../README.md)**

## Pre-requisites

- Install [ZAP](https://www.zaproxy.org/download/)
  - This will be used to exercise the WAF
  
## Introduction

Azure Web Application Firewall in Azure Front Door provides extensive logging and telemetry to help you understand how your web application firewall (WAF) is performing and the actions it takes.

The Azure Front Door WAF log is integrated with Azure Monitor. Azure Monitor enables you to track diagnostic information, including WAF alerts and logs. You can configure WAF monitoring within the Azure Front Door resource in the Azure portal under the Diagnostics tab, through infrastructure as code approaches, or by using Azure Monitor directly.

The Azure Front Door WAF provides detailed reporting on each request and each threat that it detects. Logging is integrated with Azure's diagnostics logs and alerts by using Azure Monitor logs.

Logs aren't enabled by default. You must explicitly enable logs. You can configure logs in the Azure portal by using the Diagnostic settings tab. If logging is enabled and a WAF rule is triggered, any matching patterns are logged in plain text to help you analyze and debug the WAF policy behavior. You can use exclusions to fine-tune rules and exclude any data that you want to be excluded from the logs. For more information, see [Azure Web Application Firewall monitoring and logging](https://learn.microsoft.com/en-us/azure/web-application-firewall/afds/waf-front-door-monitor?pivots=front-door-standard-premium)

## Description

For this challenge we are going to:
1. Configure Azure Front Door Diagnostic Logs  - [Reference](https://learn.microsoft.com/en-us/azure/frontdoor/standard-premium/how-to-logs)
    - Select both audit and allLogs Category groups
2. Trigger Automated Scan thru ZAP 


## Success Criteria
- Show requests that were logged thru Front Door's logs
- Demonstrate Usage analytics thru [built-in reports](https://learn.microsoft.com/en-us/azure/frontdoor/standard-premium/how-to-reports?tabs=traffic-by-domain) 
- Monitor Blocked traffic by running Kusto Query - [Reference](https://learn.microsoft.com/en-us/azure/web-application-firewall/afds/waf-front-door-monitor?pivots=front-door-standard-premium#waf-logs)

## Reference video recording
[Challenge 4](https://microsoft-my.sharepoint.com/:v:/p/sandeepgadey/EfA-u1vPfR9JkPLwAGK5-IwBv7lYHouvwl4OZkWyAaOH2g?e=dEW6Ja&nav=eyJyZWZlcnJhbEluZm8iOnsicmVmZXJyYWxBcHAiOiJTdHJlYW1XZWJBcHAiLCJyZWZlcnJhbFZpZXciOiJTaGFyZURpYWxvZy1MaW5rIiwicmVmZXJyYWxBcHBQbGF0Zm9ybSI6IldlYiIsInJlZmVycmFsTW9kZSI6InZpZXcifX0%3D)


## Learning Resources

- [Azure Front Door Rules Engine Matching Criteria](https://docs.microsoft.com/en-us/azure/frontdoor/front-door-rules-engine-match-conditions)
- [Azure Front Door Rules Engine Actions](https://docs.microsoft.com/en-us/azure/frontdoor/front-door-rules-engine-actions)

