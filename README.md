# What happens when you type a website address?

**Example** 

You type:
```
https://shorterloop.com
```
into you browser and press enter.

Although it looks instant, but several things happen behind the scene before the page appears.

##  Stage 1: DNS lookup (Finding the server)
The browser only undersnts **IP addresses**, not the domain names.

So the first step is to ask a DNS server(domain name system).

```
What is the IP address of shorterloop.com?
```

**Example**

shorterloop.com > DNS(Cloudflare) > IP address (76.xx.xx.xx)

You can you check it by yourself:

**windows**
```
nslookup shorterloop.com
```

**Linxux**
```
dig shorterloop.com +short
```

Once the browser finds the IP address, it can can contact the server.


##  Stage 2: TCP(transmission control protocol)

**Handshake/opening the pipe/opening connection**

It performs **3 way handshake**


Think of it like talking on a phone:

```
B: Can we talk? (SYNC)
S: Yes.(SYNC+ACK)
B: Great (ACK)
```

##  Stage 3: TLS handshake
Because the website uses HTTPS, the communication must encypted.

During TLS:
- The sever sends the SSL certificate
- Browser verifies
- Both agrees on enc. keys
-  A secure connection is established.

Browser 
🔒 
Encrypted Connection 
🔒 
Server


This protects password, payments and personal data

##  Stage 4: HTTP

Now browser can ask for the web page and its associated pages.

GET
/
Host: shorterloop.com
Status code: 200 (OK)
301: Caching

along with the html page it also download all related assets(images, scripts everything.)

You can watch these requests in Chrome DevTools → Network.

##  Stage 5: Render

Now the browser begins building the page.

HTML parser + CSS parsing + Layout + paint the page.
# how-a-website-opens-in-the-browser
