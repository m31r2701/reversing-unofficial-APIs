# Reversing unofficial APIs
Resources for reverse engineering web and mobile apps for the specific purpose of discovering and using “unofficial APIs” for OSINT / SOCMINT (and other purposes). 

Before considering unofficial APIs, it is often worth checking whether or not the net platform publishes an official public / open / free API that will get you what you need.

## Tools
### Discovery
#### General
- [Wireshark](https://www.wireshark.org)
- [Portswigger Burp Suite](https://portswigger.net/burp/releases/professional-community-2024-1-1-6?requestededition=community&requestedplatform=)
- [OWASP ZAP](https://www.zaproxy.org)

#### Web apps
- Browser devtools

#### Mobile apps
- [Ghidra](https://github.com/NationalSecurityAgency/ghidra)

### Testing and using
- curl
- Postman

## Reading
### Discovery
#### General
- [*API Discovery: 15 ways to find APIs*](https://nordicapis.com/api-discovery-15-ways-to-find-apis/)
- [*Discover APIs* section on unofficial APIs](https://stevesie.com/docs/discover-apis#unofficial-apis)
- [*How To Find API Endpoints Of A Website: A Complete Guide*](https://techreviewgarden.com/how-to-find-api-endpoints-of-a-website/)

#### Web apps
- [*Finding Undocumented APIs*](https://inspectelement.org/apis.html)

#### Mobile apps
- [*How to use Ghidra to reverse engineer mobile application*](https://infosecwriteups.com/how-to-use-ghidra-to-reverse-engineer-mobile-application-c2c89dc5b9aa)
- [*Reverse engineering an Android application*](https://epic.blog/reverse-engineering/2020/07/27/reverse-engineering-android-app.html)
- [*Can ZAP be used to test mobile apps?*](https://www.zaproxy.org/faq/can-zap-be-used-to-test-mobile-apps/)
- [Use Burp Suite for mobile testing](https://portswigger.net/burp/documentation/desktop/mobile)

## Examples
- [Rolstenhouse/unofficial-apis](https://github.com/Rolstenhouse/unofficial-apis)

### Third-party / unofficial clients
- [Telethon](https://github.com/LonamiWebs/Telethon)

### OSINT / SOCMINT tools
- [Instaloader](https://github.com/instaloader/instaloader/tree/master)
- [WhatsMyName](https://github.com/WebBreacher/WhatsMyName)

### "Alternative frontends"
- [mendel5/alternative-front-ends](https://github.com/mendel5/alternative-front-ends)
- [Invidious](https://github.com/iv-org/invidious)
- [Nitter](https://github.com/zedeus/nitter)

## Disclaimer
Reversing unofficial APIs and using them may violate terms of service depending on the platform and, in certain circumstances, the laws of your country. The information presented here is for educational purposes only: I am neither responsible nor liable for your actions. Do no evil.
