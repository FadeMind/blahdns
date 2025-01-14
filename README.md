 [![HitCount](http://hits.dwyl.io/ookangzheng/blahdns.svg)](http://hits.dwyl.io/ookangzheng/blahdns) 
 
<p align="center">
  &nbsp;&nbsp;
  All donations are welcome and any amount of money will help me to maintain this project 🥰 
  <br> Around 40 EUR per month 
</p> 

## Announcements
* Dnscryptv2 `UDP` connection having performance issue though it has been fixed with new `KEYS`, make sure to check it out the [LATEST Configuration](https://github.com/ookangzheng/blahdns/blob/master/client-conf/dnscrypt/dnscrypt-proxy.toml) ... !!! 
* Bye Google Analytics, Welcome GoatCounter... BlahDNS site now use GoatCounter and we degoogled !!! (Google Analytics) 2021-04-24
* DNS over QUIC - Draft 2 `quic://dot-jp.blahdns.com:784` | `quic://dot-sg.blahdns.com:784` | `quic://dot-ch.blahdns.com:784` | `quic://dot-fi.blahdns.com:784` | `quic://dot-de.blahdns.com:784` (feedback needed)
* iOS 14 and Big Sur native DoT / DoH config file, check out [https://encrypted-dns.party/](https://encrypted-dns.party/) | Credit to: [@nitrohorse](https://gitlab.com/nitrohorse/ios14-encrypted-dns-mobileconfigs/-/tree/master)
* For more old announcements, go [here](https://github.com/ookangzheng/blahdns/issues/36)

## Our features

* Block Trackers, Ads, Malwares
* No ECS, DNSSEC ready, No logs, OpenNIC, Eth TLD, Yggdrasil 
* Both trackers are blocked by default. 
`data.mob.com, google-analytics, googleadservices, amazon-adsystem, crashlytics.com analytics.yahoo, doubleclick.net, hm.baidu.com, etc.. `
* Support http://matoken.eth/ | http://mesh.ygg/ | http://i2pd.ygg/ | http://blahdns.oss/ | https://i❤.ws/

## DoH CDN

```
https://doh1.blahdns.com/uncensor 
https://doh2.blahdns.com/uncensor 
https://doh1.blahdns.com/dns-query (censored)
https://doh2.blahdns.com/dns-query (censored)
```

## Curl with DoH for testing purpose
```
// Censored 
curl --doh-url https://doh-jp.blahdns.com/dns-query https://ssl.google-analytics.com
// Return 
curl: (7) Failed to connect to ssl.google-analytics.com port 443: Connection refused

// Uncensor
curl --doh-url https://doh-jp.blahdns.com/uncensor https://ssl.google-analytics.com
// Return
<HTML><HEAD><meta http-equiv="content-type" content="text/html;charset=utf-8">
<TITLE>301 Moved</TITLE></HEAD><BODY>
<H1>301 Moved</H1>
The document has moved
<A HREF="https://www.google.com/analytics/">here</A>.
</BODY></HTML>
```

## How to setup / config DoH DoT Dnscrypt 👇
Config: [HERE for more details](https://github.com/ookangzheng/blahdns/tree/master/server-conf)

## Server status
* Server status [UpTimeRobot](https://stats.blahdns.com) | [Dnsprivacy.org](https://dnsprivacy.org/jenkins/job/dnsprivacy-monitoring/)

## Server architecture

```bash
Server (Switzerland, Germany, Finland, Japan, Singapore)

|-- Knot-resolver (DNS resolver, OpenNIC, ICANN, Yggdrasil, ETH)
|-- Dnsdist (cache, loadbalance)
|   |   |-- DNSCryptv2 (encrypted-dns-server, port 8443)
|   |   |-- Dnsproxy (DoQ, port 784)
|   |-- doh-server (DoH, GET, POST -- m13253)
|   |   |-- |-- DoH (HAProxy, port 443, TLS 1.3, require SNI)
|-- DoT (HAProxy, port 853, TLS 1.3, require SNI)

```

## Config file / Client
* Collection of blocklist use in BlahDNS: [Source](https://github.com/ookangzheng/blahdns/raw/master/hosts/source.txt) 
* Yggdrasil IPv6 Network: [Setup guide](https://github.com/ookangzheng/blahdns/blob/master/client-conf/yggdrasil.md)
* Android DoH/DoT: [Nebulo App](https://play.google.com/store/apps/details?id=com.frostnerd.smokescreen) | [personalDNSfilter App](https://zenz-solutions.de/personaldnsfilter/) | [Intra](https://play.google.com/store/apps/details?id=app.intra)
* iOS Dnscryptv2/DoH: [Dnscloak](https://itunes.apple.com/app/dnscloak-secure-dns-client/id1452162351)
* Dnscryptv2: [dnscrypt-proxy](https://github.com/DNSCrypt/dnscrypt-proxy)
* Config files: [ Client config example ](https://github.com/ookangzheng/blahdns/tree/master/client-conf)

## Awesome dns-resolver
https://gist.github.com/ookangzheng/c8fba46fe1dbcc8152e3231f53f91e86

## Huge thanks to those OSS and ORG
1. [Knot-resolver](https://github.com/CZ-NIC/knot-resolver)
2. [m13253](https://github.com/m13253/dns-over-https)
3. [DNSPrivacy.org](https://dnsprivacy.org)

## Buy me some coffee :coffee: 

<p align="center">  
  <a href="https://www.paypal.com/paypalme/okz5289tw?locale.x=en_GB"><img alt="Donate using Paypal" src="https://www.paypalobjects.com/en_US/i/btn/btn_donateCC_LG.gif"></a>
  &nbsp;&nbsp;
  <a href='https://ko-fi.com/P5P4GPQ8' target='_blank'><img height='36' style='border:0px;height:36px;' src='https://az743702.vo.msecnd.net/cdn/kofi4.png?v=0' border='0' alt='Buy Me a Coffee at ko-fi.com' /></a>
</p>

## DISCLAIMER
* This is a HOBBY service. The operator does not guarantee in any way the access, availability and continuity of the functioning of this service. 
* Use at your own risk. Under no circumstances will the operator be held responsible or liable in any way for any claims, damages, losses, expenses, costs or liabilities whatsoever (including, without limitation, any direct or indirect damages for loss of profits, business interruption or loss of information) resulting or arising directly or indirectly from accessing or otherwise using this service (Blahdns server).
* By using this website and service you consent to the disclaimer and agree to its terms and conditions.

[![Stargazers over time](https://starchart.cc/ookangzheng/blahdns.svg)](https://starchart.cc/ookangzheng/blahdns)
