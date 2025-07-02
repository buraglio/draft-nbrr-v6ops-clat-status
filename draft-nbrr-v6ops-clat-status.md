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

informative:
RFC6877:
RFC6145:
RFC6146:
RFC6052:

--- abstract

Since publication in April 2013, 464XLAT as defined in [RFC6877] has made a prolific impact on mobile networks wishing to
implement endpoints without the presence of IPv4. This has allowed the IPv6 Internet to expand dramatically. In the same time frame, IPv6
deployments across wireline and enterprise-style networks has slowly increased, experiencing a similar albeit slower
increase in both dual-stack and, beginning around 2021, IPv6-only. This increase in IPv6-only deployments has highlighted the
Importance of 464XLAT in enabling access to legacy resources. Inclusion of the translation 464XLAT technology, and specifically the 
client side translator (CLAT) technology as either a default addition or a user-installable feature has been a notable enabler of a more seamless migration
of off legacy IP. This document reports our findings in both the availability and operational performance of the CLAT
feature and identifies remaining issues in providing ubiquitous and efficient CLAT support on a global scale.

--- middle

# Introduction

TODO Introduction

# Terminology

   464XLAT: A set of technologies that enable IPv6-only networks to access IPv4 services by 
            combining stateful and stateless translation mechanisms as defined by [RFC6877].

   PLAT:   As defined in [RFC6877], PLAT is provider-side translator (XLAT) that complies with
           [RFC6146].  It translates N:1 global IPv6 addresses to global
           IPv4 addresses, and vice versa.

   CLAT:    As defined in [RFC6877], CLAT is customer-side translator (XLAT) that complies with
           [RFC6145].  It algorithmically translates 1:1 private IPv4
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
           Section 3.3 of [RFC6052].  The CLAT does not facilitate
           communications between a local IPv4-only node and an IPv6-
           only node on the Internet.

# Availability 

# Behavior and Performance

# Security Considerations

TODO Security


# IANA Considerations

This document has no IANA actions.


--- back

# Acknowledgments
{:numbered="false"}

TODO acknowledge.
