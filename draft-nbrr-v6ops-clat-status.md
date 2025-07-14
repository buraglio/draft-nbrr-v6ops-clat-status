---
title: "A Survey of the Current State of CLAT Availability and Performance on Non-Mobile Systems"
abbrev: "CLAT Status"
category: info

docname: draft-nbrr-v6ops-clat-status-latest
submissiontype: IETF  # also: "independent", "editorial", "IAB", or "IRTF"
number:
date:
consensus: true
v: 3
area: "Operations and Management"
workgroup: "IPv6 Operations"
keyword:
 - IPv6
 - DNS64
 - PREF64
 - NAT64
 - CLAT
venue:
  group: "IPv6 Operations"
  type: "Working Group"
  mail: "v6ops@ietf.org"
  arch: "https://mailarchive.ietf.org/arch/browse/v6ops/"
  github: "buraglio/draft-nbrr-v6ops-clat-status"
  latest: "https://buraglio.github.io/draft-nbrr-v6ops-clat-status/draft-nbrr-v6ops-clat-status.html"

author:
 -
    fullname: Nick Buraglio
    organization: Energy Sciences Network
    email: "buraglio@forwardingplane.net"
 -
    fullname: Ryan Rearden
    organization: Energy Sciences Network
    email: "reardenrt@gmail.com"

normative:
   RFC6877:
informative:
   RFC6145:
   RFC6146:
   RFC6052:
   RFC8781:
   RFC7050:
   RFC8925:
   LinuxCLAT:
      target: https://github.com/toreanderson/clatd
      title: "CLAT / SIIT-DC Edge Relay implementation for Linux"

--- abstract

This document reports findings in the availability and operational performance of the client side translator (CLAT) feature
within 464XLAT as defined in {{RFC6877}}. It also identifies remaining issues in providing ubiquitous and efficient CLAT support
on a global scale. Since publication in April 2013, 464XLAT has made a significant impact on mobile networks wishing to
implement endpoints purely with IPv6. This has allowed the IPv6 Internet to expand dramatically as well as increase IPv6
deployments across wireline and enterprise-style networks.

--- middle

# Introduction

The increase of IPv6-only deployments since around 2021 has highlighted the importance of the 464XLAT technology, and specifically CLAT technology,
in enabling access to legacy IPv4-only resources. Inclusion of CLAT technology, as either a default addition or a user-installable feature, has been a notable enabler
of a more seamless migration off of legacy IP. The availability of client side translation has proliferated over the last several years, and many options and
implementations exist. This document details the findings of an availability study of major non-mobile operating systems and their status as a feature availability.
Additionally, basic functionality and performance is tested between varying systems using common performance testing tools.

# Terminology

   464XLAT: A set of technologies that enable IPv6-only networks to access IPv4 services by
            combining stateful and stateless translation mechanisms as defined by {{RFC6877}}.

   PLAT:   As defined in {{RFC6877}}, PLAT is provider-side translator (XLAT) that complies with
           {{RFC6146}}.  It translates N:1 global IPv6 addresses to global
           IPv4 addresses, and vice versa.

   CLAT:    As defined in {{RFC6877}}, CLAT is customer-side translator (XLAT) that complies with
           {{RFC6145}}.  It algorithmically translates 1:1 private IPv4
           addresses to global IPv6 addresses, and vice versa.  The CLAT
           function is applicable to a router or an end-node such as a
           mobile phone.  The CLAT should perform IP routing and
           forwarding to facilitate packets forwarding through the
           stateless translation even if it is an end-node.  The CLAT as
           a common home router or wireless Third Generation Partnership
           Project (3GPP) router is expected to perform gateway
           functions such as being a DHCP server and DNS proxy for local
           clients.  The CLAT uses different IPv6 prefixes for CLAT-side
           and PLAT-side IPv4 addresses and therefore does not comply
           with the sentence "Both IPv4-translatable IPv6 addresses and
           IPv4-converted IPv6 addresses SHOULD use the same prefix." in
           Section 3.3 of {{RFC6052}}.  The CLAT does not facilitate
           communications between a local IPv4-only node and an IPv6-
           only node on the Internet.

# Availability

CLAT functionality has existed as a core, automatic function of the devices operating systems in mobile devices for many years and has been
successfully deployed, supported, and expanded its footprint since its inception.  However, the availability within traditional desktop, laptop and general use
operating systems has a longer tail, with few commercial, off the shelf (COTS) operating environments possessing the same level of support for CLAT that exists in
mobile deployments. Within the confines of general use operating systems, there are four major categories that perform 99% of daily-use user-facing functions. The
following details the current support for CLAT in these four environments.

## BSD

BSD systems that support the ipfw toolkit have support for CLAT. This support must be manually enabled within the ipfw configuration and does not come on by default, allowing a more seamless
user experience by supporting DHCP option 108 as defined by {{RFC8925}}, pref64 as defined by {{RFC8781}}, or DNS activation as defined by {{RFC7050}}.

Within the official Concurrent Version System ports repository, there is a CLAT configuration daemon named gelatod which
checks for a NAT64 translator and configures the BSD packet filter to translate IPv4 packets into IPv6 packets.

## Linux

Linux has no official support. Linux systems may install 3rd party applications to support CLAT. This support must be manually installed and enabled within the configuration of the third party application. Third party support has varying levels of
support with the most common relying on DNS activation as defined by {{RFC7050}}. There is ongoing work on several options for CLAT in Linux, and an effort to include it in the base operating system but currently this effort is incomplete.

An open source SIIT-DC, {{LinuxCLAT}} implementation for Linux. 

## Microsoft Windows

There is currently no public support for CLAT in any Microsoft Windows version that is usable within a LAN environment. Implementations exist within multiple versions of Microsoft Windows but are limited to Mobile / Cellular interfaces.

## Apple MacOS

MacOS supports all manner of CLAT activation, and has a native, non-mobile-device implementation of the CLAT service as of MacOS 13.

# Behavior and Performance

Performance of CLAT implementations across major operating systems can and will have any number of factors affecting the overall performance of the internal operation. However, some simple baseline tests can be run to ascertain fundamental expectations. It should be noted, however, that on commodity desktop systems performance is not often a notable factor unless there are notable and significant amounts of packet loss which can be attributes specifically to the internal CLAT process. This is uncommon, however, as it is far more likely that upstream problems would be the root case of noticeable performance.
In these tests, a common set of parameters were used to aid in consistent outcomes. Tools involved were the same across all platforms, and based on IPerf3, a common bandwidth testing utility.

## Linux to Linux ()


## MacOS to MacOS (version 15.5)


# Security Considerations

None.

# IANA Considerations

This document has no IANA actions.


--- back

# Acknowledgments
{:numbered="false"}

TODO acknowledge.
