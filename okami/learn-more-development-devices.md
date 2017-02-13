---
title: Okami
template: default
---

# Learn More: Development Devices

# Overview

Devices connect to Murano using the [HTTPS Data
API](/murano/products/device_api/http/). As implied, this is HTTP secured by
TLS, which ensures that all communication -- especially that needed to
authenticate -- is secured and unreadable by third parties. Some devices,
particularly Arduino-based devices, don't readily handle TLS.

Enabling the "Allow development devices to connect" checkbox removes the
requirement to use HTTPS and allows straight-HTTP, which is **not** encrypted
and for which all information, including sensitive data like the CIK (private
key), is passed in plaintext and easily read by third parties. It is highly
discouraged to run in this mode, but activities -- particularly those during
the development of the device -- make doing so useful under limited
circumstances.

Development devices connecting via HTTP must authenticate using CIK (private
key). Such devices should not go into production; any devices using HTTP in
development that are intended for production should be reprovisioned when TLS
is enabled.

# Assigning Identity


