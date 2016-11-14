Kamila's `cdist` configs
======================

[cdist](www.nico.schottelius.org/software/cdist/) is pretty cool. I am using it to manage machine configuration in a bunch of places, such as my laptop, a number of servers, and who knows where else.

Good to know
------------

- `cdist` can be used to *partially* manage a host -- so for instance I can manage e.g. only the firewall and nginx on a physical machine, and also fully manage "disposable" or "simple" hosts.
- `cdist` is idempotent and aware of dependencies, so it do the Right Thing (TM) when you run it against a live host. This makes it suitable for managing long-lived, non-disposable, always-online hosts, such as my laptop.
- as is usual with `cdist`, I use a separate branch for every "configuration domain" (usually every host, unless I manage several hosts with the same config).

"Domains"/branches:
-------------------

### common

Holds stuff generic enough to be in a shared branch. The manifest here is (almost) empty.

This branch is a nice one to diff against.

Manifest: [here](https://github.com/AnotherKamila/cdist/tree/common/cdist/conf/manifest).

#### Notable things:

- programmatically manage (some of) `pf`, the *BSD firewall: the `__pf_rdr` type [TODO WIP not here yet]

### entropy

My laptop.

Manifest: [here](https://github.com/AnotherKamila/cdist/tree/entropy/cdist/conf/manifest).
