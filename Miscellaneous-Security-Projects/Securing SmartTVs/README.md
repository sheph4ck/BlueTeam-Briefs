# Securing SmartTVs

I read an article (https://cybersecuritynews.com/free-apps-turning-smart-tvs-into-proxies/) shared on LinkedIn, that explains how an SDK developer named "Bright Data," markets the world’s largest residential proxy network, claiming 150M+ IP addresses sourced via embedded software in partner apps.

---

Those "partner apps" are imbedeed in many IoT devices, specifically in SmartTVs. Some free Smart TV apps may ask for permission to use your internet connection as part of a commercial proxy network.

This allows companies—including some involved in AI data collection—to route web requests through ordinary households (like mine).

Researchers argue many users don't truly understand what they're consenting to, while the company involved says participation is voluntary and clearly disclosed.

This doesn't mean our TVs are "hacked," but it's a reminder that when an app is free, sometimes our bandwidth becomes part of the business model.

## How to combat this

As the article explains, there are a list of DNS hostnames that can be blocked at the router-level.

Per their recommendation, I logged into my home router and added these domains to my firewall's "blocked" domains:

proxyjs.brdtnet.com
proxyjs.luminatinet.com
clientsdk.bright-sdk.com
