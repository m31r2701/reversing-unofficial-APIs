# ⏮️ Awesome unofficial API reversing
Resources for reverse engineering web and native apps (especially mobile) for the specific purpose of discovering and using “unofficial APIs” (aka "undocumented APIs") for OSINT / SOCMINT and other purposes. 

Before considering unofficial APIs, it is often worth checking whether or not the target platform publishes an official public and/or free API that will get you what you need. There are some great repos on Github listing public and free APIs. 

Additionally, it may not be necessary to reverse an undocumented API yourself if someone has already published a comprehensive unofficial client. Many instances of these may also be found on Github.

### 📣 PSA for UK counterterrorism organisations

Thank you for your service.

A public API that may prove especially helpful for supporting your work is [Open Measures, formerly known as the Social Media Analysis Toolkit (SMAT)](https://openmeasures.io).

In terms of "rolling-your-own" client to directly ingest SOCMINT from unofficial APIs: given that extremists and terrorists are less likely to frequent the biggest mainstream platforms, nearly all of the places they hang out in online are trivial to grab data from reliably using the information below.

# 🧠 Pre-requisite knowledge

Provided you know how to use a computer and access the internet, you don't really need to know much else to begin exploring the world of unofficial APIs. It's also not necessary to be able to read code, program, or use specialist tools when you first start out. Knowledge and skills will be picked up gradually and easily over time if you find it interesting.

Here's an entirely optional (and opinionated) collection of extracts from Wikipedia (and other sources) which together provide a pretty good crash course in key concepts and jargon:

## Web app
> A web application (or web app) is application software that is accessed using a web browser. Web applications are delivered on the World Wide Web to users with an active network connection. [Single-page](#single-page-application-spa) and [progressive](#progressive-web-app-pwa) are two approaches for a website to seem more like a [native app](#native-app).
*Source: [Wikipedia](https://en.wikipedia.org/wiki/Web_application)*

## Native app
> In computing, native software or data-formats are those that were designed to run on a particular operating system. In a more technical sense, native code is code written specifically for a certain processor. In contrast, cross-platform software can be run on multiple operating systems and/or computer architectures. 
*Source: [Wikipedia](https://en.wikipedia.org/wiki/Native_(computing))*

## Mobile app
> A mobile application or app is a computer program or software application designed to run on a mobile device such as a phone, tablet, or watch. Mobile applications often stand in contrast to desktop applications which are designed to run on desktop computers, and [web applications](#web-app) which run in mobile web browsers rather than directly on the mobile device... Apps are broadly classified into three types: [native apps](#native-app), hybrid and [web apps](#web-app). [Native applications](#native-app) are designed specifically for a mobile operating system, typically iOS or Android. [Web apps](#web-app) are written in HTML5 or CSS and typically run through a browser. Hybrid apps are built using web technologies such as JavaScript, CSS, and HTML5 and function like web apps disguised in a native container. 
*Source: [Wikipedia](https://en.wikipedia.org/wiki/Mobile_app)*

## Single-page application (SPA)
> A single-page application (SPA) is a [web application](#web-app) or website that interacts with the user by dynamically rewriting the current web page with new data from the [web server](https://en.wikipedia.org/wiki/Web_server), instead of the default method of a web browser loading entire new pages. The goal is faster transitions that make the website feel more like a [native app](#native-app). In a SPA, a page refresh never occurs; instead, all necessary HTML, JavaScript, and CSS code is either retrieved by the browser with a single page load, or the appropriate resources are dynamically loaded and added to the page as necessary, usually in response to user actions. 
*Source: [Wikipedia](https://en.wikipedia.org/wiki/Single-page_application)*

## Progressive web app (PWA)
> A progressive web app (PWA) is an app that's built using web platform technologies, but that provides a user experience like that of a [platform-specific app](#native-app)... PWAs typically look like [platform-specific apps](#native-app) － they are usually displayed without the browser UI around them － but they are, as a matter of technology, still websites. This means they need a browser engine, like the ones in Chrome or Firefox, to manage and run them. With a [platform-specific app](#native-app), the platform OS manages the app, providing the environment in which it runs. With a PWA, a browser engine performs this background role, just like it does for normal websites. 
*Source: [Mozilla](https://developer.mozilla.org/en-US/docs/Web/Progressive_web_apps/Guides/What_is_a_progressive_web_app)*

## Web service
> A web service (WS) is either: a service offered by an electronic device to another electronic device, communicating with each other via the Internet, or a server running on a computer device, listening for [requests](#request-response) at a particular port over a network, serving web documents (HTML, [JSON](https://en.wikipedia.org/wiki/JSON), [XML](https://en.wikipedia.org/wiki/XML), images). In a web service, a web technology such as HTTP is used for transferring machine-readable file formats such as [XML](https://en.wikipedia.org/wiki/XML) and [JSON](https://en.wikipedia.org/wiki/JSON). In practice, a web service commonly provides an object-oriented web-based interface to a database server, utilized for example by another [web server](https://en.wikipedia.org/wiki/Web_server), or by a [mobile app](#mobile-app), that provides a user interface to the end-user. Many organizations that provide data in formatted HTML pages will also provide that data on their server as [XML](https://en.wikipedia.org/wiki/XML) or [JSON](https://en.wikipedia.org/wiki/JSON), often through a Web service to allow syndication. Another application offered to the end-user may be a [mashup](https://en.wikipedia.org/wiki/Mashup_(web_application_hybrid)), where a [Web server](https://en.wikipedia.org/wiki/Web_server) consumes several Web services at different machines and compiles the content into one user interface. 
*Source: [Wikipedia](https://en.wikipedia.org/wiki/Web_service)*

## Request-response
> In computer science, request–response or request–reply is one of the basic methods computers use to communicate with each other in a network, in which the first computer sends a request for some data and the second responds to the request. More specifically, it is a message exchange pattern in which a requestor sends a request message to a replier system, which receives and processes the request, ultimately returning a message in response. It is analogous to a telephone call, in which the caller must wait for the recipient to pick up before anything can be discussed. This is a simple but powerful messaging pattern which allows two applications to have a two-way conversation with one another over a channel; it is especially common in [client–server architectures](#client-server-model). For simplicity, this pattern is typically implemented in a purely [synchronous](https://en.wikipedia.org/wiki/Synchronous_serial_communication) fashion, as in [web service](#web-service) calls over HTTP, which holds a connection open and waits until the response is delivered or the timeout period expires. However, request–response may also be implemented [asynchronously](https://en.wikipedia.org/wiki/Asynchronous_serial_communication), with a response being returned at some unknown later time. When a synchronous system communicates with an asynchronous system, it is referred to as "sync over async" or "sync/async". This is common in enterprise application integration (EAI) implementations where slow aggregations, time-intensive functions, or human workflow must be performed before a response can be constructed and delivered.
*Source: [Wikipedia](https://en.wikipedia.org/wiki/Request–response)*

## Client-server model
> The client–server model is a distributed application structure that partitions tasks or workloads between the providers of a resource or service, called servers, and [service](#web-service) requesters, called clients. Often clients and servers communicate over a computer network on separate hardware, but both client and server may reside in the same system. A server host runs one or more server programs, which share their resources with clients. A client usually does not share any of its resources, but it requests content or service from a server. Clients, therefore, initiate communication sessions with servers, which await incoming requests. Examples of computer applications that use the client–server model are email, network printing, and the World Wide Web... The "client-server" characteristic describes the relationship of cooperating programs in an application. The server component provides a function or service to one or many clients, which initiate requests for such services. Servers are classified by the services they provide. For example, a web server serves web pages and a file server serves computer files. A shared resource may be any of the server computer's software and electronic components, from programs and data to processors and storage devices. The sharing of resources of a server constitutes a service... Generally, a service is an abstraction of computer resources and a client does not have to be concerned with how the server performs while fulfilling the request and delivering the response. The client only has to understand the response based on the well-known application protocol, i.e. the content and the formatting of the data for the requested service. Clients and servers exchange messages in a [request–response messaging pattern](#request-response). The client sends a request, and the server returns a response. This exchange of messages is an example of inter-process communication. To communicate, the computers must have a common language, and they must follow rules so that both the client and the server know what to expect. The language and rules of communication are defined in a communications protocol. All protocols operate in the application layer. The application layer protocol defines the basic patterns of the dialogue. To formalize the data exchange even further, the server may implement an application programming interface (API). The API is an abstraction layer for accessing a service. By restricting communication to a specific content format, it facilitates parsing. By abstracting access, it facilitates cross-platform data exchange.
*Source: [Wikipedia](https://en.wikipedia.org/wiki/Client–server_model)*

## Frontend and backend
> In software engineering, the terms frontend and backend (sometimes written as back end or back-end) refer to the separation of concerns between the presentation layer (frontend), and the data access layer (backend) of a piece of software, or the physical infrastructure or hardware. In the [client–server model](#client-server-model), the client is usually considered the frontend and the server is usually considered the backend, even when some presentation work is actually done on the server itself... The frontend communicates with backend through an API. In the case of [web](#web-app) and [mobile](#mobile-app) frontends, the API is often based on HTTP [request/response](#request-response). The API is sometimes designed using the "Backend for Frontend" (BFF) pattern, that serves responses to ease the processing on frontend side.
*Source: [Wikipedia](https://en.wikipedia.org/wiki/Frontend_and_backend)*

## TODO
- [Web server](https://en.wikipedia.org/wiki/Web_server)
- [XMLHttpRequest](https://en.wikipedia.org/wiki/XMLHttpRequest)
- [Dynamic webpage](https://en.wikipedia.org/wiki/Dynamic_web_page)
- [Responsive web design](https://en.wikipedia.org/wiki/Responsive_web_design)
- [API](https://en.wikipedia.org/wiki/API)
- [Web API](https://en.wikipedia.org/wiki/Web_API)
- [OpenAPI](https://en.wikipedia.org/wiki/OpenAPI_Specification)
- [REST](https://en.wikipedia.org/wiki/REST)
- [GraphQL](https://en.wikipedia.org/wiki/GraphQL)
- [Access token](https://en.wikipedia.org/wiki/Access_token)
- [Ajax](https://en.wikipedia.org/wiki/Ajax_(programming))
- [Webhook](https://en.wikipedia.org/wiki/Webhook)
- [WebSocket](https://en.wikipedia.org/wiki/WebSocket)

Afterwards, it's worth reading *TCP/IP* Chapter 9, Section 4 [*TCP/IP Key Applications and Application Protocols*](http://www.tcpipguide.com/free/t_TCPIPKeyApplicationsandApplicationProtocols.htm), more specifically [the content in this section relating to HTTP](http://www.tcpipguide.com/free/t_TCPIPWorldWideWebWWWTheWebandtheHypertextTransferP.htm).

Although reversing unofficial APIs is demonstrably **not** API hacking, documentation from Portswigger on [API testing](https://portswigger.net/web-security/api-testing) and [GraphQL](https://portswigger.net/web-security/graphql), as well as [OWASP](https://owasp.org/API-Security/editions/2023/en/0x00-header/) and the [Portswigger mapping to OWASP](https://portswigger.net/web-security/api-testing/top-10-api-vulnerabilities), are informative.

# 👀 Discovery
Reconnaissance and enumeration phase.

## Techniques
- [*API Discovery: 15 ways to find APIs*](https://nordicapis.com/api-discovery-15-ways-to-find-apis/)
- [*Discover APIs* section on unofficial APIs](https://stevesie.com/docs/discover-apis#unofficial-apis)
- [*How To Find API Endpoints Of A Website: A Complete Guide*](https://techreviewgarden.com/how-to-find-api-endpoints-of-a-website/)
- [soxoj](https://github.com/soxoj)'s [Hardcore OSINT : Reversing social media mechanisms](https://www.youtube.com/watch?v=0yQRf0Mx-hc)
### Web apps (inc. PWAs)
- [*Finding Undocumented APIs*](https://inspectelement.org/apis.html)
- [Scraping XHR](https://scrapism.lav.io/scraping-xhr/)
- [How to use undocumented web APIs](https://jvns.ca/blog/2022/03/10/how-to-use-undocumented-web-apis/)
- [Computational research in the post-API age](https://dfreelon.org/publications/2018_Computational_research_in_the_postAPI_age.pdf)
- [Web scraping 201: Finding the API](http://www.gregreda.com/2015/02/15/web-scraping-finding-the-api/)
- https://owasp.org/www-project-web-security-testing-guide/stable/4-Web_Application_Security_Testing/12-API_Testing/01-Testing_GraphQL this is worth reading as it provides useful content on GraphQL APIs. However, bear in mind that unofficial API reversing is NOT ipso facto about hunting for 0days or trying to exploit the application (unless you are, for instance, participating in a recognised bug bounty program or on a pentest engagement).
### Native apps (inc. mobile)
#### Android
- [MASTG-TECH-0003: Obtaining and extracting apps](https://mas.owasp.org/MASTG/techniques/android/MASTG-TECH-0003/)
- [MASTG-TECH-0005: Installing apps](https://mas.owasp.org/MASTG/techniques/android/MASTG-TECH-0005/)
- [MASTG-TECH-0007: Exploring the app package](https://mas.owasp.org/MASTG/techniques/android/MASTG-TECH-0007/)
- [MASTG-TECH-0010: Basic network monitoring/sniffing](https://mas.owasp.org/MASTG/techniques/android/MASTG-TECH-0010/)
- [MASTG-TECH-0011: Setting up an interception proxy](https://mas.owasp.org/MASTG/techniques/android/MASTG-TECH-0011/)
- [MASTG-TECH-0012: Bypassing certificate pinning](https://mas.owasp.org/MASTG/techniques/android/MASTG-TECH-0012/)
- [MASTG-TECH-0013: Reverse engineering Android apps](https://mas.owasp.org/MASTG/techniques/android/MASTG-TECH-0013/)
- [MASTG-TECH-0022: Information gathering - Network communication](https://mas.owasp.org/MASTG/techniques/android/MASTG-TECH-0022/)
- [MASTG-TECH-0028: Get open connections](https://mas.owasp.org/MASTG/techniques/android/MASTG-TECH-0028/)
#### iOS
- [MASTG-TECH-0054: Obtaining and extracting apps](https://mas.owasp.org/MASTG/techniques/ios/MASTG-TECH-0054/)
- [MASTG-TECH-0056: Installing apps](https://mas.owasp.org/MASTG/techniques/ios/MASTG-TECH-0056/)
- [MASTG-TECH-0058: Exploring the app package](https://mas.owasp.org/MASTG/techniques/ios/MASTG-TECH-0058/)
- [MASTG-TECH-0062: Basic network monitoring/sniffing](https://mas.owasp.org/MASTG/techniques/ios/MASTG-TECH-0062/)
- [MASTG-TECH-0063: Setting up an interception proxy](https://mas.owasp.org/MASTG/techniques/ios/MASTG-TECH-0063/)
- [MASTG-TECH-0064: Bypassing certificate pinning](https://mas.owasp.org/MASTG/techniques/ios/MASTG-TECH-0064/)
- [MASTG-TECH-0065: Reverse engineering iOS apps](https://mas.owasp.org/MASTG/techniques/ios/MASTG-TECH-0065/)
- [MASTG-TECH-0074: Information gathering - Network communication](https://mas.owasp.org/MASTG/techniques/ios/MASTG-TECH-0074/)
- [MASTG-TECH-0088: Emulation-based analysis](https://mas.owasp.org/MASTG/techniques/ios/MASTG-TECH-0088/)
## 🛠️ Tools
Note, many of these tools imply a black-box scenario. If the target platform is fully open source or even partly so, it may be possible to enumerate unofficial API endpoints by simply reading the source code. There may also be official documentation publicly available that will help with this and serve as an aide-mémoire when you come to the "fuzzing" and "collection" phases of the process.
- [Wireshark](https://www.wireshark.org)
- [Portswigger Burp Suite](https://portswigger.net/burp/releases/professional-community-2024-1-1-6?requestededition=community&requestedplatform=)
- [OWASP ZAP](https://www.zaproxy.org)
- [weAudit VSCode extension](https://blog.trailofbits.com/2024/03/19/read-code-like-a-pro-with-our-weaudit-vscode-extension/) for taking notes while reading an open-source codebase
### Web apps (inc. PWAs)
- Browser devtools
- https://owasp.org/www-project-web-security-testing-guide/stable/6-Appendix/A-Testing_Tools_Resource
### Native apps (inc. mobile)
- https://mas.owasp.org/MASTG/tools/
- [Ghidra](https://github.com/NationalSecurityAgency/ghidra)
- [*How to use Ghidra to reverse engineer mobile application*](https://infosecwriteups.com/how-to-use-ghidra-to-reverse-engineer-mobile-application-c2c89dc5b9aa)
- [*Can ZAP be used to test mobile apps?*](https://www.zaproxy.org/faq/can-zap-be-used-to-test-mobile-apps/)
- [Use Burp Suite for mobile testing](https://portswigger.net/burp/documentation/desktop/mobile)
#### Android
- [Android Emulator, packaged with Android Studio](https://developer.android.com/studio/run/emulator)
- https://apkcombo.com
- https://www.hackthebox.com/blog/intro-to-mobile-pentesting
- https://petruknisme.medium.com/complete-beginners-guide-to-setup-android-pentest-lab-without-physical-device-4f7b9e945d11
- https://medium.com/swlh/android-mobile-penetration-testing-lab-dfb8ceb4efbd
- https://medium.com/@prnz_offl/android-pentesting-lab-setup-the-ultimate-how-to-d7aacf84c984
- https://medium.com/purplebox/step-by-step-guide-to-building-an-android-pentest-lab-853b4af6945e
- https://portswigger.net/burp/documentation/desktop/mobile/config-android-device
- https://blog.yarsalabs.com/setting-up-burp-for-android-application-testing/
- https://thezero.org/blog/2016/01/25/android_proxy_zap/
- [*Reverse engineering an Android application*](https://epic.blog/reverse-engineering/2020/07/27/reverse-engineering-android-app.html)

# 📚 Documentation
If you are mapping several endpoints, and especially if you are attempting a comprehensive unofficial client build, it is worth documenting in detail what you find during the discovery phase. You may wish to consider keeping track of requests and responses in full (including payloads, headers, etc.). There are also tools used by developers of official APIs to document their implementation that work just as well for reverse engineers of unofficial APIs.

# 🧪 Fuzzing
Testing phase to check everything works. This isn't really an independent stage: it's an experimental cycle which bridges the gap between (and overlaps with) the discovery and collection phases.

Early on, you may (optionally) want to use these tools to make easy and quick test requests to endpoints you have found:

- curl
- Postman

Some may be more comfortable using the same programming language they elect to use in the collection phase. For example, I usually reach straight for Python rather than using either of the above. 

If you like Python, Jupyter Notebooks are excellent for documenting test requests before (if you are planning to) starting work on building an application in your preferred language to use the unofficial API.

After running your test request(s), you may be reviewing enumerated data (or generating new data) if an error occurred, running further tests on the same or different endpoints, or moving onto the collection phase. 

# 🧑‍🌾 Collection
Requests made and data returned from API for your specific purpose.

## 🐍 Python
- requests
- BeautifulSoup4
- asyncio

## 🤷‍♂️ Don't know how to code?
- Jan Lauridtsen's 2024 SANS OSINT Summit lecture *[Uncovering the invisible gold mines: How to dump raw data from TikTok](https://youtube.com/watch?v=MQumdWDR0C4)* on dumping raw data from apps built with a React frontend. [Jan's Github repo for this talk here](https://github.com/janhalendk/react).

# 🏃‍♂️Evading detection
There are various techniques that can be used to prevent a platform detecting and blocking an unofficial API client:

- Browser emulation arouses less suspicion
- User agent switching, provided contradictory and / or unique fingerprint not emitted by your client
  - Note: anti-fingerprinting measures, beyond user agent switching, quickly get complex and there's a continual arms race between fingerprinters / anti-fingerprinters
- IP rotation: works better with residential rather than with data centre IP addresses typically provided by VPNs or proxies - this is likely to be quite expensive, however. [Using AWS Lambda for easy-mode IP rotation or even an array of dongles to get mobile / cell IPs are also inventive strategies](https://incolumitas.com/2021/11/03/so-you-want-to-scrape-like-the-big-boys/)
- Cloudflare evasion: several methods include trawling Shodan and Censys for server IPs behind Cloudflare IPs (exposed as a result of misconfiguration) to bypass Cloudflare - this is usually the most productive approach, though is not the only one. Do not accidentally DOS or DDOS the service - even if it's an unintentional, this will be illegal if (as seems likely) you do not own the service or have permission from the owner.

As with anti-fingerprinting, block evasion in general is a complex and fast changing area. The hard work will be ensuring the code you write today continues to work as fingerprinting and anti-bot measures evolve. This dynamism is compounded by target sites occasionally refactoring their APIs. Always stay on the right side of the law and don't do anything that you will be unable to defend (possibly in a court of law).

# Examples
- [Rolstenhouse/unofficial-apis](https://github.com/Rolstenhouse/unofficial-apis)

## OSINT / SOCMINT tools
- [Instaloader](https://github.com/instaloader/instaloader/tree/master)
- [WhatsMyName](https://github.com/WebBreacher/WhatsMyName)

## Stories
- The prologue of [Darknet Diaries Episode 120: Voulnet](https://darknetdiaries.com/transcript/120/)
- The main narrative of [Darknet Diaries Episode 84: Jet-setters](https://darknetdiaries.com/transcript/84/)

## Use in journalism and academic research
- https://gizmodo.com/ring-s-hidden-data-let-us-map-amazons-sprawling-home-su-1840312279
- https://www.theguardian.com/us-news/2022/aug/25/porch-piracy-package-thefts-doorstep-delivery
- https://site.dcalacci.net/papers/ring-cscw-2021.pdf
- https://www.pnas.org/doi/full/10.1073/pnas.1717781115
- https://source.opennews.org/articles/freeing-plum-book/

## "Alternative frontends"
- [mendel5/alternative-front-ends](https://github.com/mendel5/alternative-front-ends)
- [Invidious](https://github.com/iv-org/invidious)
- [Nitter](https://github.com/zedeus/nitter)

# ⁉️ Isn't this just web scraping but with more steps?

There is an undeniable degree of overlap between conventional web scraping and unofficial API reversing. Nevertheless, considering the latter to be merely a subset of web scraping ignores the fact that when people talk about "web scraping" they really mean "screen scraping": parsing and extracting data from the DOM of a rendered webpage (even using computer vision tech to grab imagery as well as text). Unofficial API reversing has the same objective (i.e., extracting data) but has its own set of methods (beyond some common approaches), and it does neither the topic at hand nor web scraping any favours by conflating the two. Sometimes when you're reaching for an unofficial means of extracting data, web scraping will be the tool you need and at other times unofficial APIs will be.

# ⚖️ Disclaimer

Reversing unofficial APIs and using them may violate terms of service depending on the platform and, in certain circumstances, the laws of your country. Legal risks are similar to those described on the [Wikipedia entry on web scraping](https://en.wikipedia.org/wiki/Web_scraping#Legal_issues), though they will vary given how marked the difference can be in approach between unofficial API reversing and conventional web scraping. Legal threats around [reverse engineering](https://en.wikipedia.org/wiki/Reverse_engineering#Legality) are worth looking into to supplement the aforementioned. The information presented here is for educational purposes only: I am neither responsible nor liable for your actions. Do no evil.
