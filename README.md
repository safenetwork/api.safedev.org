# SAFE API Docs

[SAFE Launcher](https://maidsafe.readme.io/docs/launcher) exposes a REST API that apps can use to interact with the SAFE Network.

[Download **SAFE Launcher v0.10.0**](https://github.com/maidsafe/safe_launcher/releases/tag/0.10.0) to use **SAFE API v0.6**.

[Read the **SAFE Dev Tutorials**](https://tutorials.safedev.org/) to see examples of how to use the SAFE API.

### What is SAFE Launcher?

SAFE Launcher enables you to build SAFE Network apps that don't require users to give you access to their network credentials (their account secret and account password). This means users only have to share their network credentials with SAFE Launcher and not with every app they use. Apps only interact with the SAFE Network indirectly via SAFE Launcher, which can be thought of as the single point of contact with the network.

### What is the SAFE Network?

The SAFE Network is a decentralized data storage and communications network that provides a secure, efficient and low-cost infrastructure for everyone.

Rather than using data centers and servers which are prone to data theft and surveillance, the SAFE Network uses advanced peer-to-peer technology that joins together the unused hard drive space, CPU power and Internet connections of all SAFE users, creating a global network.

Users of the SAFE Network have full control over their data, while app developers can focus their time building on top of a secure infrastructure.

### How do I use the SAFE API?

Apps can make HTTP requests to `http://localhost:8100`. This is a local REST server that is automatically started when the user opens SAFE Launcher.

It's possible to build SAFE Network apps in many environments (e.g. Windows, macOS, Linux, web browsers, etc.) and pretty much any programming language (e.g. JavaScript, Python, Go, Ruby, Rust, C#, etc.) since the requirements for using the SAFE API are very minimal (you just need to be able to make HTTP requests).

### Desktop apps

Examples of desktop apps:

* [SAFE Demo App](https://github.com/maidsafe/safe_examples/tree/master/demo_app)
* [SAFE Mail Tutorial](https://tutorials.safedev.org/email-app/)

### Web apps

To access SAFE websites, we recommend using [SAFE Browser v0.4.2](https://github.com/joshuef/beaker/releases/tag/v0.4.2). SAFE Browser provides an API that web apps can use to communicate with SAFE Launcher. See the [SAFE-js API Docs](https://github.com/joshuef/safe-js#api) for more info.

Examples of web apps:

* [SAFE Comment Tutorial](https://tutorials.safedev.org/website-with-comments/)
* [SAFE Signaling Demo](https://tutorials.safedev.org/webrtc-video-chat-app/)
* [SAFE Markdown Editor](https://tutorials.safedev.org/markdown-editor/)
