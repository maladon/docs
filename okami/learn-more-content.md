---
title: Okami
template: default
---

# Learn More: Content

# Overview

Files uploaded as content are available to devices for download. Each content
item has an id, a mime type, a size (in bytes), and a timestamp. Devices may
[list available content](/murano/products/device_api/http/#list-available-content),
[get content info](/murano/products/device_api/http/#get-content-info), and
[download content](/murano/products/device_api/http/#download-content) using
the [HTTP Device API](/murano/products/device_api/http/).

There is no restriction as to the kind of content that can be made available to
devices here -- they can contain anything from audio/video content to config
data -- but the typical use case is to store firmware updates. For content that
gets updated over time, such as with new firmware versions, it is recommended
to include in the id some kind of version tag. Whether this approach is taken
or the content is updated in place and timestamp is used to differentiate,
devices will need a means to know which version they're at. Exosite recommends
storing this information in a [Resource](/okami/learn-more-resources/).
Additionally, if the resource is cloud-modifiable, the device can be notified
when new firmware is available.

Content items must be less than 64 MB in size.
