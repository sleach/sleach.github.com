---
layout: post
title: Amazon.com eating it’s own (Cloudfront) dog food
---

{{ page.title }}
================

<p class="meta">03 July 2012 - Colorado</p>

I was curious, given the amazing rate Amazon has been improving "Cloudfront":http://aws.amazon.com/cloudfront/, if they had decided to eat their own dog food yet and use it as the primary CDN on their crown jewel – the main Amazon.com site.  They had previously entrusted Akamai for the majority of their CDN needs.

Long story short – absolutely.  Of the 163 external resources on the main page, 74 of them are hosted on Cloudfront – compared to 46 on Akamai (the rest are a mixture of doubleclick, etc.).  That’s pretty impressive.

h2. More detail

I used the following methodology to come up with the numbers.  My first step was to use the always-awesome Webpagetest.org to get a dump of all of the external resources – i.e. Javascript, CSS etc. (you can see my report here – to get the external resources you can click on “Raw object data” to get a CSV of each object).  From that CSV, I just wrote a quick python script that would use Dnspython on each external hostname, do a lookup, and see if the CNAME pointed to Cloudfront, Akamai, or something else.

Below is a dump of all of the URL’s, sorted by count with their hosting CDN.

g-ecx.images-amazon.com, for example, is hosted on Cloudfront:

```
;; ANSWER SECTION:
g-ecx.images-amazon.com. 49 IN CNAME d1ge0kk1l5kms0.cloudfront.net.
d1ge0kk1l5kms0.cloudfront.net. 14 IN CNAME d1ge0kk1l5kms0.iad12.cloudfront.net.
while z-ecx.images-amazon.com is hosted on Akamai:

;; ANSWER SECTION:
z-ecx.images-amazon.com. 60 IN CNAME z-ecx.images-amazon.com.edgesuite.net.
z-ecx.images-amazon.com.edgesuite.net. 8725 IN CNAME a1248.g.akamai.net.
```

Full breakdown.

    g-ecx.images-amazon.com => 56 (cloudfront)
    z-ecx.images-amazon.com => 27 (akamai)
    images-na.ssl-images-amazon.com => 15 (akamai)
    www.amazon.com => 10 (Other)
    s.amazon-adsystem.com => 8 (Other)
    ecx.images-amazon.com => 8 (cloudfront)
    ad.doubleclick.net => 6 (Other)
    c.amazon-adsystem.com => 5 (cloudfront)
    pda-as.amazon.com => 4 (Other)
    fls-na.amazon.com => 4 (Other)
    s0.2mdn.net => 3 (Other)
    d2o307dm5mqftz.cloudfront.net => 2 (cloudfront)
    pda-bes.amazon.com => 2 (Other)
    ads.pubmatic.com => 2 (Other)
    d3l3lkinz3f56t.cloudfront.net => 2 (cloudfront)
    tag.admeld.com => 1 (akamai)
    c.www.endless.com => 1 (cloudfront)
    image4.pubmatic.com => 1 (Other)
    tap.rubiconproject.com => 1 (Other)
    sis.amazon.com => 1 (Other)
    bid.openx.net => 1 (Other)
    ocsp.comodoca.com => 1 (Other)
    cm.g.doubleclick.net => 1 (Other)
    image3.pubmatic.com => 1 (Other)

Kudos to Amazon for making the move.
