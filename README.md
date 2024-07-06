# ⏮️ Awesome unofficial API reversing
Resources for reverse engineering web and native apps (especially mobile) for the specific purpose of discovering and using “unofficial APIs” (aka "undocumented APIs") for OSINT / SOCMINT and other purposes. 

Before considering unofficial APIs, it is often worth checking whether or not the target platform publishes an official public and/or free API that will get you what you need. There are some great repos on Github listing public and free APIs. 

Additionally, it may not be necessary to reverse an undocumented API yourself if someone has already published a comprehensive unofficial client. Many instances of these may also be found on Github.

### 📣 PSA for UK counterterrorism organisations

Thank you for your service.

A public API that may prove especially helpful for supporting your work targeting XRW individuals and groups is [Open Measures, formerly known as the Social Media Analysis Toolkit (SMAT)](https://openmeasures.io).

In terms of "rolling-your-own" client to directly ingest SOCMINT from unofficial APIs: given that extremists and terrorists (in general not just the XRW) typically don't frequent the biggest mainstream platforms (with one exception), nearly all of the places they hang out in online are trivial to grab data from reliably using the information below.

## 🧠 Pre-requisite knowledge

Provided you know how to use a computer and access the internet, you don't really need to know much else to begin exploring the world of unofficial APIs. It's also not necessary to be able to read code, program, or use specialist tools when you first start out. Knowledge and skills will be picked up gradually and easily over time if you find it interesting.

Here's an entirely optional (and opinionated) list of pages on Wikipedia that give a pretty good crash course in concepts and jargon:

- [Web 2.0](https://en.wikipedia.org/wiki/Web_2.0)
- [Web service](https://en.wikipedia.org/wiki/Web_service)
- [Request-response](https://en.wikipedia.org/wiki/Request–response)
- [Client-server model](https://en.wikipedia.org/wiki/Client–server_model)
- [Frontend and backend](https://en.wikipedia.org/wiki/Frontend_and_backend)
- [Web server](https://en.wikipedia.org/wiki/Web_server)
- [XML](https://en.wikipedia.org/wiki/XML)
- [XMLHttpRequest](https://en.wikipedia.org/wiki/XMLHttpRequest)
- [Web app](https://en.wikipedia.org/wiki/Web_application)
- [Dynamic webpage](https://en.wikipedia.org/wiki/Dynamic_web_page)
- [Responsive web design](https://en.wikipedia.org/wiki/Responsive_web_design)
- [Single-page application](https://en.wikipedia.org/wiki/Single-page_application)
- [Progressive web app](https://en.wikipedia.org/wiki/Progressive_web_app)
- [Mobile app](https://en.wikipedia.org/wiki/Mobile_app)
- [API](https://en.wikipedia.org/wiki/API)
- [Web API](https://en.wikipedia.org/wiki/Web_API)
- [OpenAPI](https://en.wikipedia.org/wiki/OpenAPI_Specification)
- [JSON](https://en.wikipedia.org/wiki/JSON)
- [REST](https://en.wikipedia.org/wiki/REST)
- [GraphQL](https://en.wikipedia.org/wiki/GraphQL)
- [Mashup](https://en.wikipedia.org/wiki/Mashup_(web_application_hybrid))
- [Access token](https://en.wikipedia.org/wiki/Access_token)
- [Synchronous](https://en.wikipedia.org/wiki/Synchronous_serial_communication)
- [Asynchronous](https://en.wikipedia.org/wiki/Asynchronous_serial_communication)
- [Ajax](https://en.wikipedia.org/wiki/Ajax_(programming))
- [Webhook](https://en.wikipedia.org/wiki/Webhook)
- [WebSocket](https://en.wikipedia.org/wiki/WebSocket)

Afterwards, it's worth reading *TCP/IP* Chapter 9, Section 4 [*TCP/IP Key Applications and Application Protocols*](http://www.tcpipguide.com/free/t_TCPIPKeyApplicationsandApplicationProtocols.htm), more specifically [the content in this section relating to HTTP](http://www.tcpipguide.com/free/t_TCPIPWorldWideWebWWWTheWebandtheHypertextTransferP.htm).

Although reversing unofficial APIs is demonstrably **not** API hacking, documentation from Portswigger on [API testing](https://portswigger.net/web-security/api-testing) and [GraphQL](https://portswigger.net/web-security/graphql), as well as [OWASP](https://owasp.org/API-Security/editions/2023/en/0x00-header/) and the [Portswigger mapping to OWASP](https://portswigger.net/web-security/api-testing/top-10-api-vulnerabilities), are informative.

## 👀 Discovery
Reconnaissance and enumeration phase.

### General
Note, many of the tools in this discovery section imply a black-box scenario. If the target platform is fully open source or even partly so, it may be possible to enumerate unofficial API endpoints by simply reading the source code. There may also be official documentation publicly available that will help with this and serve as an aide-mémoire when you come to the "fuzzing" and "collection" phases of the process.

#### 🛠️ Tools
- [Wireshark](https://www.wireshark.org)
- [Portswigger Burp Suite](https://portswigger.net/burp/releases/professional-community-2024-1-1-6?requestededition=community&requestedplatform=)
- [OWASP ZAP](https://www.zaproxy.org)
- [weAudit VSCode extension](https://blog.trailofbits.com/2024/03/19/read-code-like-a-pro-with-our-weaudit-vscode-extension/) for taking notes while reading an open-source codebase
- https://owasp.org/www-project-web-security-testing-guide/stable/6-Appendix/A-Testing_Tools_Resource

#### 📖 Reading
- [*API Discovery: 15 ways to find APIs*](https://nordicapis.com/api-discovery-15-ways-to-find-apis/)
- [*Discover APIs* section on unofficial APIs](https://stevesie.com/docs/discover-apis#unofficial-apis)
- [*How To Find API Endpoints Of A Website: A Complete Guide*](https://techreviewgarden.com/how-to-find-api-endpoints-of-a-website/)

#### 📼 Watch
- [soxoj](https://github.com/soxoj)'s [Hardcore OSINT : Reversing social media mechanisms](https://www.youtube.com/watch?v=0yQRf0Mx-hc)

### Web apps (inc. PWAs)
#### 🛠️ Tools
Any of the General tools for discovery, plus:
- Browser devtools

#### 📖 Reading
- [*Finding Undocumented APIs*](https://inspectelement.org/apis.html)
- [Scraping XHR](https://scrapism.lav.io/scraping-xhr/)
- [How to use undocumented web APIs](https://jvns.ca/blog/2022/03/10/how-to-use-undocumented-web-apis/)
- [Computational research in the post-API age](https://dfreelon.org/publications/2018_Computational_research_in_the_postAPI_age.pdf)
- [Web scraping 201: Finding the API](http://www.gregreda.com/2015/02/15/web-scraping-finding-the-api/)
- https://owasp.org/www-project-web-security-testing-guide/stable/4-Web_Application_Security_Testing/12-API_Testing/01-Testing_GraphQL this is worth reading as it provides useful content on GraphQL APIs. However, bear in mind that unofficial API reversing is NOT ipso facto about hunting for 0days or trying to exploit the application (unless you are, for instance, participating in a recognised bug bounty program or on a pentest engagement).

### Native apps (inc. mobile apps)
#### 🛠️ Tools
Any of the General tools for discovery, plus:
- [Ghidra](https://github.com/NationalSecurityAgency/ghidra)
- [Android Emulator, packaged with Android Studio](https://developer.android.com/studio/run/emulator)
- https://mas.owasp.org/MASTG/tools/
- https://apkcombo.com

#### 📖 Reading
- [*How to use Ghidra to reverse engineer mobile application*](https://infosecwriteups.com/how-to-use-ghidra-to-reverse-engineer-mobile-application-c2c89dc5b9aa)
- [*Reverse engineering an Android application*](https://epic.blog/reverse-engineering/2020/07/27/reverse-engineering-android-app.html)
- [*Can ZAP be used to test mobile apps?*](https://www.zaproxy.org/faq/can-zap-be-used-to-test-mobile-apps/)
- [Use Burp Suite for mobile testing](https://portswigger.net/burp/documentation/desktop/mobile)

##### Android
- https://www.hackthebox.com/blog/intro-to-mobile-pentesting
- https://petruknisme.medium.com/complete-beginners-guide-to-setup-android-pentest-lab-without-physical-device-4f7b9e945d11
- https://medium.com/swlh/android-mobile-penetration-testing-lab-dfb8ceb4efbd
- https://medium.com/@prnz_offl/android-pentesting-lab-setup-the-ultimate-how-to-d7aacf84c984
- https://medium.com/purplebox/step-by-step-guide-to-building-an-android-pentest-lab-853b4af6945e
- https://portswigger.net/burp/documentation/desktop/mobile/config-android-device
- https://blog.yarsalabs.com/setting-up-burp-for-android-application-testing/
- https://thezero.org/blog/2016/01/25/android_proxy_zap/
- [MASTG-TECH-0010: Basic network monitoring/sniffing](https://mas.owasp.org/MASTG/techniques/android/MASTG-TECH-0010/)
- [MASTG-TECH-0011: Setting up an interception proxy](https://mas.owasp.org/MASTG/techniques/android/MASTG-TECH-0011/)
- [MASTG-TECH-0022: Information gathering - Network communication](https://mas.owasp.org/MASTG/techniques/android/MASTG-TECH-0022/)
- [MASTG-TECH-0003: Obtaining and extracting apps](https://mas.owasp.org/MASTG/techniques/android/MASTG-TECH-0003/)
- https://mas.owasp.org/MASTG/techniques/android/MASTG-TECH-0005/
- https://mas.owasp.org/MASTG/techniques/android/MASTG-TECH-0013/
- https://mas.owasp.org/MASTG/techniques/android/MASTG-TECH-0028/
- https://mas.owasp.org/MASTG/techniques/android/MASTG-TECH-0012/
- https://mas.owasp.org/MASTG/techniques/android/MASTG-TECH-0007/

##### iOS
- https://mas.owasp.org/MASTG/techniques/ios/MASTG-TECH-0074/
- https://mas.owasp.org/MASTG/techniques/ios/MASTG-TECH-0065/
- https://mas.owasp.org/MASTG/techniques/ios/MASTG-TECH-0056/
- https://mas.owasp.org/MASTG/techniques/ios/MASTG-TECH-0063/
- https://mas.owasp.org/MASTG/techniques/ios/MASTG-TECH-0064/
- https://mas.owasp.org/MASTG/techniques/ios/MASTG-TECH-0088/
- https://mas.owasp.org/MASTG/techniques/ios/MASTG-TECH-0062/
- https://mas.owasp.org/MASTG/techniques/ios/MASTG-TECH-0058/
- https://mas.owasp.org/MASTG/techniques/ios/MASTG-TECH-0054/
- https://mas.owasp.org/MASTG/techniques/ios/MASTG-TECH-0065/

## 📚 Documentation
If you are mapping several endpoints, and especially if you are attempting a comprehensive unofficial client build, it is worth documenting in detail what you find during the discovery phase. You may wish to consider keeping track of requests and responses in full (including payloads, headers, etc.). There are also tools used by developers of official APIs to document their implementation that work just as well for reverse engineers of unofficial APIs.

## 🧪 Fuzzing
Automated and manual testing phase to check everything works.
- curl
- Postman

## 🧑‍🌾 Collection
Requests made and data returned from API for your specific purpose.

### 🐍 Python
- requests
- BeautifulSoup4
- asyncio

### 🤷‍♂️ Don't know how to code?
- Jan Lauridtsen's 2024 SANS OSINT Summit lecture *[Uncovering the invisible gold mines: How to dump raw data from TikTok](https://youtube.com/watch?v=MQumdWDR0C4)* on dumping raw data from apps built with a React frontend. [Jan's Github repo for this talk here](https://github.com/janhalendk/react).

## 🏃‍♂️Evading detection
There are various techniques that can be used to prevent a platform detecting and blocking an unofficial API client:

- Browser emulation arouses less suspicion
- User agent switching, provided contradictory and / or unique fingerprint not emitted by your client
  - Note: anti-fingerprinting measures, beyond user agent switching, quickly get complex and there's a continual arms race between fingerprinters / anti-fingerprinters
- IP rotation: works better with residential rather than with data centre IP addresses typically provided by VPNs or proxies - this is likely to be quite expensive, however. [Using AWS Lambda for easy-mode IP rotation or even an array of dongles to get mobile / cell IPs are also inventive strategies](https://incolumitas.com/2021/11/03/so-you-want-to-scrape-like-the-big-boys/)
- Cloudflare evasion: several methods include trawling Shodan and Censys for server IPs behind Cloudflare IPs (exposed as a result of misconfiguration) to bypass Cloudflare - this is usually the most productive approach, though is not the only one. Do not accidentally DOS or DDOS the service - this is likely to be illegal.

As with anti-fingerprinting, block evasion in general is a complex and fast changing area. The hard work will be ensuring the code you write today continues to work as fingerprinting and anti-bot measures evolve. This dynamism is compounded by target sites occasionally refactoring their APIs. Always stay on the right side of the law and don't do anything that you will be unable to defend (possibly in a court of law).

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

## ⁉️ Isn't this just that web scraping thing i've head about but with more steps?

There is an undeniable degree of overlap between conventional web scraping and unofficial API reversing. Nevertheless, considering the latter to be merely a subset of web scraping ignores the fact that when people talk about "web scraping" they really mean "screen scraping": parsing and extracting data from the DOM of a rendered webpage (even using computer vision tech to grab imagery as well as text). Unofficial API reversing has the same objective (i.e., extracting data) but has its own set of methods (beyond some common approaches), and it does neither the topic at hand nor web scraping any favours by conflating the two. Sometimes when you're reaching for an unofficial means of extracting data, web scraping will be the tool you need and at other times unofficial APIs will be.

## ⚖️ Disclaimer

Reversing unofficial APIs and using them may violate terms of service depending on the platform and, in certain circumstances, the laws of your country. Legal risks are similar to those described on the [Wikipedia entry on web scraping](https://en.wikipedia.org/wiki/Web_scraping#Legal_issues), though they will vary given how marked the difference can be in approach between unofficial API reversing and conventional web scraping. Legal threats around [reverse engineering](https://en.wikipedia.org/wiki/Reverse_engineering#Legality) are worth looking into to supplement the aforementioned. The information presented here is for educational purposes only: I am neither responsible nor liable for your actions. Do no evil.
