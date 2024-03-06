---
layout: post
title: "How I Finally Enabled SSL Certificates on My GitHub Pages Websites"
date: "2024-03-06 23:33:00 +0300"
permalink: /:title
---

For many years, my websites hosted on GitHub Pages lacked the crucial HTTPS protocol. Initially, it seemed like a feature that wasn't available, but a recent encounter with a GitHub-hosted site using Jekyll piqued my curiosity. I decided it was time to explore whether I could also add the SSL magic to my websites. Surprisingly, the process turned out to be quite simple.

## The Old A Records:

Previously, my A records looked like this:

- 192.30.252.153
- 192.30.252.154

## The New A Records:

To enable SSL, I had to update the A records to the following:

- 185.199.108.153
- 185.199.109.153
- 185.199.110.153
- 185.199.111.153

## The AAAA Records:

Additionally, I needed to add AAAA records:

- 2606:50c0:8000::153
- 2606:50c0:8001::153
- 2606:50c0:8002::153
- 2606:50c0:8003::153

This task was particularly cumbersome because GoDaddy, my domain registrar, insisted on verifying multiple times that it was indeed me making the DNS changes.

## Enforcing HTTPS

The setting to enforce HTTPS can be found in the repository settings under Pages and Custom Domain. All it took was a simple tick of the box, and I was good to go—once GitHub figured out the updated DNS records.

## Conclusion

Enabling SSL certificates on my GitHub Pages websites was a long-overdue task that turned out to be much simpler than I anticipated. With a few DNS record updates and a checkbox tick, I finally joined the ranks of secure website owners. If you're in a similar situation, don't hesitate to make the switch—it's easier than you think and well worth the effort in terms of security and user trust.

