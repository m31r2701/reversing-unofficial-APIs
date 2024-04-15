# Awesome unofficial API reversing
Resources for reverse engineering web and native apps (especially mobile) for the specific purpose of discovering and using “unofficial APIs” (aka "undocumented APIs") for OSINT / SOCMINT and other purposes. 

Before considering unofficial APIs, it is often worth checking whether or not the target platform publishes an official public and/or free API that will get you what you need. There are some great repos on Github listing public and free APIs.

Additionally, it may not be necessary to reverse an undocumented API yourself if someone has already published a comprehensive unofficial client. Many instances of these may also be found on Github.

## Pre-requisite knowledge
### Concepts
- https://en.wikipedia.org/wiki/API
- https://en.wikipedia.org/wiki/Client–server_model
- https://en.wikipedia.org/wiki/Frontend_and_backend
- https://en.wikipedia.org/wiki/Communication_endpoint
- https://en.wikipedia.org/wiki/Request–response
- https://en.wikipedia.org/wiki/Synchronous_serial_communication
- https://en.wikipedia.org/wiki/Asynchronous_serial_communication
- https://en.wikipedia.org/wiki/Web_2.0
- https://en.wikipedia.org/wiki/Web_server
- https://en.wikipedia.org/wiki/Mobile_app
- https://en.wikipedia.org/wiki/Access_token
- https://en.wikipedia.org/wiki/Web_service
- https://en.wikipedia.org/wiki/Mashup_(web_application_hybrid)

### HTTP
- TCP/IP Chapter 9, Section 4 [*TCP/IP Key Applications and Application Protocols*](http://www.tcpipguide.com/free/t_TCPIPKeyApplicationsandApplicationProtocols.htm), more specifically [the content in this section relating to HTTP](http://www.tcpipguide.com/free/t_TCPIPWorldWideWebWWWTheWebandtheHypertextTransferP.htm)

### Web apps
- https://en.wikipedia.org/wiki/Web_application
- https://en.wikipedia.org/wiki/Responsive_web_design
- https://en.wikipedia.org/wiki/Dynamic_web_page

#### SPAs
- https://en.wikipedia.org/wiki/Single-page_application
- https://business.adobe.com/blog/basics/differences-between-traditional-web-apps-and-single-page-apps
- https://www.spiceworks.com/tech/devops/articles/what-is-single-page-application/#_002

#### PWAs
- https://en.wikipedia.org/wiki/Progressive_web_app

### Web APIs
- https://en.wikipedia.org/wiki/Web_API
- https://en.wikipedia.org/wiki/Ajax_(programming)
- https://en.wikipedia.org/wiki/XMLHttpRequest
- https://en.wikipedia.org/wiki/WebSocket
- https://en.wikipedia.org/wiki/XML
- https://en.wikipedia.org/wiki/JSON
- https://en.wikipedia.org/wiki/Webhook
- https://en.wikipedia.org/wiki/OpenAPI_Specification
- https://en.wikipedia.org/wiki/REST
- https://en.wikipedia.org/wiki/GraphQL

## Discovery
Reconnaissance and enumeration phase.

### General
Note, many of the tools in this discovery section imply a black-box scenario. If the target platform is fully open source or even partly so, it may be possible to enumerate unofficial API endpoints by simply reading the source code. There may also be official documentation publicly available that will help with this and serve as an aide-mémoire when you come to the "fuzzing" and "collection" phases of the process.

#### Tools
- [Wireshark](https://www.wireshark.org)
- [Portswigger Burp Suite](https://portswigger.net/burp/releases/professional-community-2024-1-1-6?requestededition=community&requestedplatform=)
- [OWASP ZAP](https://www.zaproxy.org)

#### Reading
- [*API Discovery: 15 ways to find APIs*](https://nordicapis.com/api-discovery-15-ways-to-find-apis/)
- [*Discover APIs* section on unofficial APIs](https://stevesie.com/docs/discover-apis#unofficial-apis)
- [*How To Find API Endpoints Of A Website: A Complete Guide*](https://techreviewgarden.com/how-to-find-api-endpoints-of-a-website/)

#### Watch
- [soxoj](https://github.com/soxoj)'s [Hardcore OSINT : Reversing social media mechanisms](https://www.youtube.com/watch?v=0yQRf0Mx-hc)
- Jan Lauridtsen's 2024 SANS OSINT Summit lecture *[Uncovering the invisible gold mines: How to dump raw data from TikTok](https://youtube.com/watch?v=MQumdWDR0C4)* on dumping raw data from apps built with a React frontend.

### Web apps (inc. PWAs)
#### Tools
Any of the General tools for discovery, plus:
- Browser devtools

#### Reading
- [*Finding Undocumented APIs*](https://inspectelement.org/apis.html)
- [Scraping XHR](https://scrapism.lav.io/scraping-xhr/)
- [How to use undocumented web APIs](https://jvns.ca/blog/2022/03/10/how-to-use-undocumented-web-apis/)
- [Computational research in the post-API age](https://dfreelon.org/publications/2018_Computational_research_in_the_postAPI_age.pdf)
- [Web scraping 201: Finding the API](http://www.gregreda.com/2015/02/15/web-scraping-finding-the-api/)

### Native apps (inc. mobile apps)
#### Tools
Any of the General tools for discovery, plus:
- [Ghidra](https://github.com/NationalSecurityAgency/ghidra)

#### Reading
- [*How to use Ghidra to reverse engineer mobile application*](https://infosecwriteups.com/how-to-use-ghidra-to-reverse-engineer-mobile-application-c2c89dc5b9aa)
- [*Reverse engineering an Android application*](https://epic.blog/reverse-engineering/2020/07/27/reverse-engineering-android-app.html)
- [*Can ZAP be used to test mobile apps?*](https://www.zaproxy.org/faq/can-zap-be-used-to-test-mobile-apps/)
- [Use Burp Suite for mobile testing](https://portswigger.net/burp/documentation/desktop/mobile)

## Documentation
If you are mapping several endpoints, and especially if you are attempting a comprehensive unofficial client build, it is worth documenting in detail what you find during the discovery phase. You may wish to consider keeping track of requests and responses in full (including payloads, headers, etc.). There are also tools used by developers of official APIs to document their implementation that work just as well for reverse engineers of unofficial APIs.

## Fuzzing
Automated and manual testing phase to check everything works.
- curl
- Postman

## Collection
Requests made and data returned from API for your specific purpose.

### Python
- requests
- BeautifulSoup4
- asyncio

## Evading detection
There are various techniques that can be used to prevent a platform detecting and blocking an unofficial API client.

## Examples
- [Rolstenhouse/unofficial-apis](https://github.com/Rolstenhouse/unofficial-apis)

### OSINT / SOCMINT tools
- [Instaloader](https://github.com/instaloader/instaloader/tree/master)
- [WhatsMyName](https://github.com/WebBreacher/WhatsMyName)

### Stories
- The prologue of [Darknet Diaries Episode 120: Voulnet](https://darknetdiaries.com/transcript/120/)
- The main narrative of [Darknet Diaries Episode 84: Jet-setters](https://darknetdiaries.com/transcript/84/)

### Use in journalism and academic research
- https://gizmodo.com/ring-s-hidden-data-let-us-map-amazons-sprawling-home-su-1840312279
- https://www.theguardian.com/us-news/2022/aug/25/porch-piracy-package-thefts-doorstep-delivery
- https://site.dcalacci.net/papers/ring-cscw-2021.pdf
- https://www.pnas.org/doi/full/10.1073/pnas.1717781115
- https://source.opennews.org/articles/freeing-plum-book/

### "Alternative frontends"
- [mendel5/alternative-front-ends](https://github.com/mendel5/alternative-front-ends)
- [Invidious](https://github.com/iv-org/invidious)
- [Nitter](https://github.com/zedeus/nitter)

## Disclaimer
Reversing unofficial APIs and using them may violate terms of service depending on the platform and, in certain circumstances, the laws of your country. The information presented here is for educational purposes only: I am neither responsible nor liable for your actions. Do no evil.
