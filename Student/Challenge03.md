# Challenge 3 - Provision a Web Application Firewall (WAF)

[< Previous Challenge [2]](./Challenge02.md)&nbsp;&nbsp;-&nbsp;&nbsp;**[Home](../README.md)**&nbsp;&nbsp;-&nbsp;&nbsp;[Next Challenge [4] >](./Challenge06.md)

## Introduction

User experience is dramatically better, you are seeing orders from all over the world come in. Your done right?  Nope, we remember now that the Internet can be a scary place...  You start seeing some really strange requests URL in your logs that end with:

- %3Btype%20%25SYSTEMROOT%25%5Cwin.ini
- %3Bvar%20cd%3Bvar%20d%3Dnew%20Date%28%29%3Bdo%7Bcd%3Dnew%20Date%28%29%3B%7Dwhile%28cd-d%3C8000%29
- %3Bping%20-n%209%20localhost
- %60%2Fbin%2Fcat%20%2Fetc%2Fpasswd%60

Looks like someone is trying to snoop around ...

This is where a Web Application Firewall (WAF) comes into play.  **Web Application Firewall** (Layer 7) refers to a capability (either a physical network appliance or a virtual network appliance) that can analyze and mitigate based on the payload of 1 to many packets that constitutes a specific HTTP/HTTPS request.  So instead of just being able to say "don't allow requests from IP Address X", it can be "don't allow GET requests to URL Y".  This is particularly powerful due to the nature of [complicated attacks that involve specific HTTP request patterns](https://en.wikipedia.org/wiki/Web_application_security) (either thru the Query String or posted body's) that are indicative to a particular web application platform.

For Azure this means using a [Web Application Firewall Policy with Front Door](https://docs.microsoft.com/en-us/azure/web-application-firewall/afds/afds-overview#waf-policy-and-rules).  The WAF Policies for Azure support Custom Rules sets to allow or deny requests by Client IP(s), payload, or by [Geographic area](https://docs.microsoft.com/en-us/azure/frontdoor/front-door-tutorial-geo-filtering).  WAF Policies also have Rule Sets you can apply, one referred to as the "Default Rule Set", are a set of rules defined by [OWASP (Open Web Application Security Project)](https://owasp.org/).  These [rules](https://github.com/coreruleset/coreruleset) individually targeted various forms of web attack and exploit strategies.  

***IMPORTANT** - When implementing WAF's, even in an emergency, it's a best practice to implement in what Azure's WAF Policy refers to as ["detection" mode](https://docs.microsoft.com/en-us/azure/web-application-firewall/afds/afds-overview#waf-modes), which doesn't actively block.  This will allow you to review (quickly in an emergency) activity going thru the WAF to ensure a rule isn't being too aggressive (i.e. blocking) when acting on traffic.*

*Another strategy is to turn on a WAF in Prevention mode but change all the individual rules to have an action of ["Log"](https://docs.microsoft.com/en-us/azure/web-application-firewall/afds/afds-overview#waf-actions), which will still show the rule in effect, but not block traffic.*

For the purpose of this challenge, you will go straight to Prevention mode.  You may also choose to put the WAF into Detection mode than switch it, but the end success criteria will need to demonstrate blocked requests.


## Description

For this challenge we are going to:
1. Provision a Azure Web Application Firewall Policy - [Reference](https://learn.microsoft.com/en-us/azure/web-application-firewall/afds/waf-front-door-create-portal)
   1. Configure the Default Rule Set
   2. Add a Custom rule to allow only the country you are currently located.
   3. Change WAF Policy to Prevention Mode
2. With a Browser window open to [https://tools.keycdn.com/performance](https://tools.keycdn.com/performance), test the frontdoor.***SITENAME***.contosocsalabs.com performance.
   - You should see several of the requests fail now for the 

## Success Criteria

- Demonstrate the website still works thru Front Door via https://frontdoor.***SITENAME***.contosocsalabs.com 
  - ***HINT*** - You will see **x-azure-ref** in the Response Headers of each request to Front Door.

- Demonstrate the geofiltering rule is blocking requests for countries other than your own

## Reference video recording
[Challenge 3](https://microsoft-my.sharepoint.com/:v:/p/sandeepgadey/EdOPA0H7f2VBuT7eb4wX3LMBKfv11ZBzqJH7FDUCstsqKw?e=1sNue4&nav=eyJyZWZlcnJhbEluZm8iOnsicmVmZXJyYWxBcHAiOiJTdHJlYW1XZWJBcHAiLCJyZWZlcnJhbFZpZXciOiJTaGFyZURpYWxvZy1MaW5rIiwicmVmZXJyYWxBcHBQbGF0Zm9ybSI6IldlYiIsInJlZmVycmFsTW9kZSI6InZpZXcifX0%3D)


## Learning Resources

- [Azure Front Door WAF](https://docs.microsoft.com/en-us/azure/web-application-firewall/afds/afds-overview)
- [Azure Front Door Diagnostic Logs](https://docs.microsoft.com/en-us/azure/frontdoor/front-door-diagnostics#diagnostic-logging)
- [Azure Logging](https://docs.microsoft.com/en-us/azure/azure-monitor/platform/platform-logs-overview)

