---
title: Okami
template: default
---

# Learn More: Provisioning

# Overview

Provisioning is the process by which a device acquires credentials, which
consist of an identity and a secure means of verifying that identity. Murano
supports many different verification methods, including a CIK (private key) and
TLS/SSL certificates.

Devices connecting for the first time may do so fully provisioned -- presenting
both identity and verification of that identity -- may present only their
identity, or may require being given both an identity and verification; of
these, devices fully provisioned as part of the manufacturing process are
considered the most secure, as they can not be spoofed and the private aspect
of the verification needn't be sent to them; provisioning opens the possibility
that illegitimate devices can appear as legitimate and be granted access.

When provisioning a device, the device may present its own identity (assuming
"Allow devices to register their own identity" is selected). Such devices will
have an identity (such as a MAC address) that must match the specified format.
Alternatively, a device may receive an identity (when "Allow server to generate
the identity for devices connecting without one" is selected). In either case,
it is possible for illegitimate devices to successfully provision; presented
identity provides a slightly greater barrier due to it's identity format
validation. It is possible to further restrict provisioning to only those
devices with particular IP Addresses.
