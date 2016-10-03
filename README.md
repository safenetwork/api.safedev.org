# SAFE API Docs

[SAFE Launcher](https://maidsafe.readme.io/docs/launcher) exposes a REST API that apps can use to interact with the SAFE Network.

**[Download SAFE Launcher](https://maidsafe.net/alpha.html)** to use the SAFE API.

**[Read the SAFE Dev Tutorials](https://tutorials.safedev.org/)** to see examples of how to use the SAFE API.

### What is SAFE Launcher?

SAFE Launcher enables you to build SAFE Network apps that don't require users to give you access to their network credentials (their account secret and account password). This means users only have to share their network credentials with SAFE Launcher and not with every app they use. Apps only interact with the SAFE Network indirectly via SAFE Launcher, which can be thought of as the single point of contact with the network.

### What is the SAFE Network?

The SAFE Network is a decentralized data storage and communications network that provides a secure, efficient and no-cost infrastructure for app developers.

Rather than using data centers and servers which are prone to data theft and surveillance, the SAFE Network uses advanced peer-to-peer technology that joins together the spare computing capacity of all SAFE users, creating a global network.

### How do I use the SAFE API?

Apps can make HTTP requests to `http://localhost:8100`. This is a local REST server that is automatically started when the user opens SAFE Launcher.

It's possible to build SAFE Network apps in many environments (e.g. Windows, macOS, Linux, web browsers, etc.) and pretty much any programming language (e.g. JavaScript, Python, Go, Ruby, Rust, C#, etc.) since the requirements for using the SAFE API are very minimal (you just need to be able to make HTTP requests).

### Desktop apps

Examples of desktop apps:

* [SAFE Demo App](https://github.com/maidsafe/safe_examples/tree/master/demo_app)
* [SAFE Mail Tutorial](https://github.com/maidsafe/safe_examples/tree/master/email_app)

### Web apps

Since web pages are supported via a web proxy, the base URL for accessing the SAFE API should be `http://api.safenet` instead of `http://localhost:8100`.

The web proxy injects CSP headers to prevent mixing clearnet with safenet.

Here are the CSP Headers:

```
default-src 'self' *.safenet; object-src 'none'; base-uri 'self'; form-action http://api.safenet; frame-ancestors *.safenet; child-src *.safenet
```

This prevents usage of inline JavaScript and CSS which is a restriction at present.
