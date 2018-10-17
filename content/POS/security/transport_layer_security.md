---
title: "Transport Layer Security"
menuTitle: "Transport Layer Security"
date: 2018-05-07T10:32:12+09:30
draft: false
weight: 1
---

<h3>Transport Layer Security</h3>

All API communications will be over <a href="https://en.wikipedia.org/wiki/HTTPS">HTTPS</a> (HTTP over TLS). The minimum supported version is TLS 1.0. That being said, we strongly recommend TLS 1.2 as this has a number of cryptographic improvements in the cipher suites.

We understand TLS 1.0 is not PCI DSS compliant, however, none of the POS APIs include any credit-card information (encrypted, encoded or otherwise) in any of the requests or responses, to and from Oxipay. As such there are no PCI DSS concerns.

The reason we support TLS 1.0 is due to the fact a lot of retailer POS systems are installed on older operating systems (e.g. Windows Server 2008 or Windows XP) that don't natively support TLS 1.1 or 1.2. The logistics of upgrading retailer operating systems or pushing the burden to POS software vendors (to find client libraries that fill in the gaps) is not viable.
