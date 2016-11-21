
# How to host a static website

## Intro
The first several sections are introductory material. If you already know how web hosting works, or if you don’t care, you can skip straight to the section labelled “getting started with static hosting”
What is hosting?
For a web site to be accessible over the internet, it needs a few things.

First, there needs to be a web server, which is a program that accepts the incoming HTML request and responds with the requested content. The web server is always hosted on a computer somewhere -- be it your computer or a company’s machine. So when we talk about hosting a website, we mean to make a web server available somewhere that can listen for incoming HTTP requests and respond with your website’s HTML, CSS, and other assets (like images or javascript).

How do I access the webserver?
Of course, it’s never that simple. In addition to hosting a web server somewhere, there needs to be a way for people to find the web server. This can be done one of two ways. First, you can go directly to the web server’s IP address, a unique 4 or 8 number string (depending on if you’re IPv4 or IPv6, respectively) to request the content. If you’ve ever hosted a web server locally, you’ve probably had to go to the IP address 127.0.0.1, which is the “loopback” IP: it points to whatever machine you’re currently on.

Of course, if I want to go to google, I should be able to go to “google.com” and not “64.233.177.102”. This is what domain names are for. Without getting too bogged down in the details, there’s a network of servers (called domain name servers, or DNSes) that every computer knows about that maintain a big lookup table that maps domain names to IP addresses. So when I go to facebook.com, what is actually happening is that my computer sends a request to a DNS, asks “where is google.com located?” and the DNS server responds “it’s at 64.233.177.102”.

So in order to have a real, easily usable website (and so you don’t look like an idiot), a working website needs two things: a web server and a domain name.

What is a static site?
A static site is the kind of site we’ve been working on all semester. It is entirely client-side, which means that all interaction with the website happens on the user’s computer. There’s no additional back and forth, until the user tries to go to a different page, such as when they click on a link. The only thing you can ask of a static site is “give me this page”.

Static sites are very limited in functionality. Most importantly, static sites cannot persist information, which means that they cannot keep permanent data between browser sessions. That means if you close the website and open it back up, you will be served the same HTML both times, even if you edited something the first time.

This may be easier to see with some examples:

Facebook is the quintessential example of a non-static site. When you click the “like” button on a post, your browser doesn’t just use javascript to increment the like count. Instead, your browser makes a “request” to facebook’s servers that contains the information such as “what did the user like” and “what is the user’s name?”. Once the like has been processed (for example, making sure that the user hasn’t already liked this post before), then facebook’s servers responds to your browser “it’s good, update the like count” (or “no good, don’t update the count”).
CSS Zen Garden is a static site. Your computer only talks to CSS Zen Garden’s servers to say “hey, give me such and such a page”. Every time you go to csszengarden.com you are seeing the same thing as everyone else (unless they switched their HTML files in between, for an update for example).

Why use static site hosting?
It is very unlikely that you will be using static site hosting professionally. Most of the web needs persistence to do anything significant, including but not limited to: social networking, admin pages, and eCommerce.

However, static sites are very useful for many personal projects -- in particular, they have become popular lately for blog hosting.

Additionally, dynamic web hosting (i.e., non-static) can be very tricky to set up, and is relatively expensive. If you’re using a subdomain of another site (for example, “jack.blogspot.com” instead of “jack.com”), static hosting is often completely free!

## Getting started with static hosting
There are a lot of really great ways to host static websites, even for free. Some great options include **Aerobatic** and **Github Pages**. Unfortunately, those can be a little tricky to use, and we’re trying to make this is as easy as possible.

So we’re going to be using a relatively new service called **Forge**.

So navigate to “https://getforge.com” and click on “Sign Up for free” -- there’s some text on here about this being a free trial, but if you stick to one site with no custom domains, it should remain free forever.

Fill out your information and you should be brought to a dashboard page.

There’s some notes on this page talking about a CDN and TurboJS. Don’t worry about that.

Next, navigate to the directory (folder) where the site that you want to host is located. Make sure that your main page is called “index.html”. Then we need to make a zip file containing your site. Instructions differ on platform:

Windows: right click on the directory containing your index.html and other files. Select “Send to > Compressed (zipped) folder”. A new zipped folder with the same name will be added in the same location. If you have file extensions disabled, you won’t see it, but this “compressed folder” is a “zip file”.

Mac: right click on the folder containing your index.html and other files. Select “compress”. A new zip file with the same name as the directory will be added to the same location.

Linux: open a terminal and navigate to the directory containing the directory containing your index.html and other files. That is, if your files are in ~/workspace/web-design/javajam you should cd into ~/workspace/web-design. Then run zip -r javajam.zip javajam. Of course, replace all instances “javajam” with the name of the directory your site is actually in. This will create a zip file in ~/workspace/web-design called javajam.zip.

Now head back to your browser and upload the zipfile to forge. That should be it! Now you just go to the domain you specified and you’ll see your website pop up!
