---
layout: post
title: Ubuntu/Canonical DOES NOT have a US based mirror for us.archive.ubuntu.com
---

{{ page.title }}
================

<p class="meta">02 July 2012 - Colorado</p>

Ubuntu’s US archive server (used by APT) always returns a /24 that is hosted in London (queried from multiple locations to make sure they weren’t using GeoIP functionality).  Side note: Verisign’s Managed DNS can help with that if you are reading this Canonical)

    ;; ANSWER SECTION:
    us.archive.ubuntu.com. 600 IN A 91.189.92.154
    us.archive.ubuntu.com. 600 IN A 91.189.92.155
    us.archive.ubuntu.com. 600 IN A 91.189.92.176
    us.archive.ubuntu.com. 600 IN A 91.189.92.177
    us.archive.ubuntu.com. 600 IN A 91.189.92.179
    us.archive.ubuntu.com. 600 IN A 91.189.92.180
    us.archive.ubuntu.com. 600 IN A 91.189.92.181
    us.archive.ubuntu.com. 600 IN A 91.189.92.182
    us.archive.ubuntu.com. 600 IN A 91.189.92.183
    us.archive.ubuntu.com. 600 IN A 91.189.92.184
    us.archive.ubuntu.com. 600 IN A 91.189.92.192
    us.archive.ubuntu.com. 600 IN A 91.189.92.193
    us.archive.ubuntu.com. 600 IN A 91.189.92.151
    us.archive.ubuntu.com. 600 IN A 91.189.92.152
    us.archive.ubuntu.com. 600 IN A 91.189.92.153

Example MTR/Traceroute from Amazon AWS US-West

    Host Loss% Snt Last Avg Best Wrst StDev
     1. ip-10-166-184-2.us-west-1.compute.internal 0.0% 4 0.4 0.6 0.3 1.4 0.5
     2. ip-10-1-4-5.us-west-1.compute.internal 0.0% 4 0.5 5.7 0.4 21.3 10.4
     3. 216.182.236.73 0.0% 4 0.7 0.7 0.6 0.7 0.1
     4. 205.251.229.107 0.0% 4 1.4 1.3 1.2 1.4 0.1
     5. 205.251.229.9 0.0% 4 2.3 8.7 2.3 20.1 8.3
     6. xe-0-0-0-0.r05.plalca01.us.bb.gin.ntt.net 0.0% 4 2.8 2.9 2.8 3.0 0.1
     7. ???
     8. ae-4.r07.snjsca04.us.bb.gin.ntt.net 0.0% 4 166.1 169.9 166.1 171.3 2.5
     9. ae-7.r20.snjsca04.us.bb.gin.ntt.net 0.0% 4 3.1 3.1 3.0 3.2 0.1
     10. ae-4.r21.asbnva02.us.bb.gin.ntt.net 0.0% 4 75.7 75.7 75.6 75.8 0.1
     11. ae-2.r23.amstnl02.nl.bb.gin.ntt.net 0.0% 4 156.8 159.9 156.8 163.7 3.5
     12. ae-1.r03.amstnl02.nl.bb.gin.ntt.net 0.0% 3 160.8 163.2 160.7 168.0 4.2
     13. te3-2-0-cr0.nik.nl.as6908.net 0.0% 3 162.9 163.7 161.2 167.1 3.1
     14. te1-4-3508-cr0.thn.uk.as6908.net 0.0% 3 172.1 190.5 172.1 206.8 17.5
     15. canonical-gw.datahop.net 0.0% 3 153.8 155.0 152.1 159.1 3.7
     16. haetae.canonical.com 0.0% 3 158.3 154.5 146.1 159.1 7.3

