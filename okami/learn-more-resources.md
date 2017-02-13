---
title: Okami
template: default
---

# Learn More: Resources

# Overview

Resources, such as temperature and status, represent a device's digital twin in
the cloud. A resource is identified by its alias and can accept a string, a
number, or a boolean value. The resource's unit (°C, etc.) can be specified to
further clarify the alias's measurement and it's possible to restrict values to
ranges (0-100) or to discrete values ("open", "closed", "jammed"). The current
resource value for a given device is visible when browsing the device in the
project and is accessible to scripts, which can then act on reported values in
any number of ways.

Typically, devices report values to resources that are "read-only" in the
cloud; it is possible to enable writing from the cloud, which can be used to
support command-and-control behavior. All resources have a "reported" value
which represents the last value written by the device (using the
[write](/murano/products/device_api/http/#write) API). Resources that are
cloud-writeable have an additional "set" value that's assigned when a write
occurs from the cloud. The [read](/murano/products/device_api/http/#read) API
will return the "set" value (not the "reported" value!) in this case; note,
however, that a device write will replace both the "set" and the "reported"
value. Devices will use either the read API or the
[long-polling](/murano/products/device_api/http/#long-polling) API to receive
control requests and then write appropriate resource updates to reflect its
having acted on the request.

Devices are not restricted to write to only defined resources. Devices write to
"alias"es which may or may not correspond to defined resources. All device
writes are sent to the event handler and can be processed by scripts, but only
writes to defined resources will have "reported" values stored, available to
devices via "read" and visible when viewing the device online. Additionally,
only resources that are cloud-modifiable will have "set" values.

To recap:

|Configuration|Device Write|Device Read|Cloud Set|Cloud Get|
|-------------|------------|-----------|---------|---------|
|No resource|sent to event handler|N/A|N/A|N/A|
|Resource, not cloud-modifiable|sent to event handler, updates "reported" value|reads "reported" value|N/A|reads "reported" value|
|Resource, cloud-modifiable|sent to event handler, updates "reported" and "set" values|reads "set" value|writes "set" value|can read both "reported" and "set" values|
