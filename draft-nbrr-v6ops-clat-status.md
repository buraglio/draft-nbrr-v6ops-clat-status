---
title: "Current State of CLAT Availability and Performance on Non-Mobile Systems"
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

TODO Abstract


--- middle

# Introduction

TODO Introduction

# Terminology

   PLAT:   As defined in [[RFC6877]], PLAT is provider-side translator (XLAT) that complies with
           [[RFC6146]].  It translates N:1 global IPv6 addresses to global
           IPv4 addresses, and vice versa.

   CLAT:    As defined in [[RFC6877]], CLAT is customer-side translator (XLAT) that complies with
           [[RFC6145]].  It algorithmically translates 1:1 private IPv4
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
           Section 3.3 of [[RFC6052]].  The CLAT does not facilitate
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
