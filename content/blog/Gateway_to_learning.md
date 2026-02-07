+++
author = "Joe W"
title = 'Gateway to Learning'
date = 2026-02-06T20:22:40-08:00
description = "002 - further up and further in."
tags = [
    "markdown",
    "Homelab",
    "journey",
    "pfSense",
    "Blog Post",
    "State Of The Lab"
]
hideReply = false
+++

##### State of the lab: pfSense

I have used pfSense as my gateway for about 7 years and I want to highlight it, given that it's where my self-hosted journey really started. Its inception was to be a simple project to get hands-on experience with a real-world networking firewall. At the time, I was in the middle of studying for my CompTIA Network+, and I was interested in a career path in networking and infrastructure. My road with pfSense has had so much learning, errors, fixes, and even some considerations of moving on. To explore these 7-years would be a fun trip down memory lane; however, it feels better suited to talk at a high-level about how and why I currently use it, with some plans for the future.

## What is pfSense?

pfSense is an open-source firewall and router that offers a free community edition license, with built-in tools and integrations to expand its base functionality (DNS, DHCP, IDS/IPS, etc.).

## Why pfSense?

I started with pfSense because it offered a free edition, it’s open-source, and is a well-known enterprise-grade tool. I have stayed with pfSense over the years for a few additional reasons; it’s reliability, fits all my needs, my existing knowledge of it, its expandable and wide functionality, custom hardware to ensure support for my exact needs, and its support & community knowledge space.

## So how do I use it?

### DNS-related uses:

Like many users on the internet, I just want to read a website and not have to deal with the latest scam pop-up. I filter out much of the noise of the internet using a network-level ADguard called pfBlockerNG. It’s used for IP & DNS (unbound) blocking and sinkholes. pfBlockerNG also gives me GeoIP filtering that I use for incoming/outgoing traffic to prevent visitors I am not expecting.

I operate quite a few services at home with my own domain for a clean URL and added security. It results in my fair share of DNS records that use a split-horizon method to keep any of that traffic at home, while actings as my main DNS server before going out to Quad9 or my fail-over DNS provider.

My Certificate Authority is hosted on pfSense and I use the integrated ACME service to manage my homelab certs. I have set up custom tooling to push out any certs automatically. I rarely need to check on my services, https and certs setup at this point.

### Security-related uses:

A firewall to control inbound and outbound connections. While simple in concept, the control of its stateful nature by default allows for great explicit control of my network. I combine this with VLANs for greater separation, control and security of what devices can access what by default, i.e. Guest Network, DMZ network, Work Network, etc. 

I also use a fair number of Aliases to group ip,ports, urls to for ease of management and consolidation of firewall rules. Which I often leverage the ability for schedules for my firewall and the traffic shaper tools to have a more limited scope and quality of connections (Gaming, video calls, streaming, etc) during certain times of day. Every bit of traffic is filtered and managed by Snort, which I use for threat detection and removal before it even starts causing a problem.

pfSense itself also offers some built-in authentication, as well as a FreeRADIUS server, to have the ability for IAM controls on the system itself for a best practice of breaking out accounts to certain scopes. Not as valuable for a one-person team, but good to know how to use and enforce some good habits of privilege v. standard accounts and MFA.

### Routing-related uses:

While pfSense is critical to navigating anywhere on the internet/my intranet using its core function as my gateway router, it also acts as a reverse proxy for some of my traffic using HAProxy to connect to some backend servers. I often use Caddy as my final SSL termination reverse proxy.

I also have quite a few managed VPN connections via my preferred method of WireGuard, for my travel router and some VPS services. While many of the ‘public’ services for friends like my game servers exist in the cloud, some still exist at home behind a VPN connection on my DMZ network.

### Other uses

pfSense also acts as my main NTP server to keep all my endpoint times in sync for time-based security (i.e. OTP) and accurate logs. It also acts as a WoL manager for certain servers. The collection of diagnostic tools and logs has been invaluable for testing, understanding and solving any network problem. Which, surprise surprise, is NOT always DNS. But, often -is.

## Future Use

While my focus is elsewhere in my current journey, I am hoping to expand my pfSense router functionality more (my last update was adding 2.5gb hardware support for my infrastructure). While not ideal to have my pfSense host be a larger single-point-of-failure than it is, I am working within a homelab scope and accept the risk. I already have a robust and tested recovery plan with a fallback instance I maintain, I have already rebuilt once and will not let it happen again. I also have enough resources that go unused on my pfSense router and would love to get my money’s worth by maximizing its use closer to an ~80% utility during normal operation.

I am planning to deploy a NUTs integration. I have a UPS that protects my homelab from power outages and provides line-conditioning, however, it’s all currently unmanaged. While most of my homelab comprises energy efficiency mini PCs that could run for some time on just the UPS battery, a NUTs host could better manage the power outage scenario to allow for an automated shutdown plan.

I would also love to expand my logging with the integrated syslog-ng server for logs. I have logging elsewhere and while it’d be great to be redundant, I’d rather have a single log aggregation server on my pfSense instance due to its default centralization. Granted, my plans of Graphana,Loki and Prometheus are my next log-focused projects for observability and dashboards.

I would also love to move my core account authentication for pfSense to an Authentik instance I self host. I also want to look into Suricata again for IDS/IPS instead of Snort, and look into Zeek for a long-term analyzer for detecting deeper, unknown threats.  

## A Final Thought

I am always juggling projects and learning, and while networking engineering is no longer my path, I believe my time with networking has built valuable experience and understanding that impacts my work; its value cannot be praised enough. 