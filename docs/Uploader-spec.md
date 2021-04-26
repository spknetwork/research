# Uploader
![](https://img.shields.io/badge/status-wip-orange.svg?style=flat-square) 
### Goals
This document serves as a brainstorming area for ideas and concepts behind the standardized service provider agnostic video encoder node.



### Terms
* `uploader`: Denotes an endpoint where an enduser can push video files over HTTP for the uploader to store and provide an IPFS CID back to the user.
* `encoder`: Denotes an endpoint where video transcoding/encoding takes place, irrespective of whether the endpoint provides upload functionality.

### Features
* Start/pause encoding process
* Start/pause upload process
* Track encoding progress
* Disconnect from encoder then reconnect and pick up last left off spot. Allow for background completion on the encoder
* Support pluggable authentication system
* Encoder can require payment
* Protocol is transport agnostic (separate from HTTP, websocket, libp2p, etc)
* Rating limiting
* Encoder node can enforce specific codec/quality presets
* Enduser can enforce specific codec/quality presets
* Encoder node is video formatting agnostic (HLS, mp4, webm)
* Encoder node can enforce removal of cached content with notification to user
* Extensible: The protocol should keep later expansion/additions as near top priority. Design decisions should take this into account.
* Modularity: The protocol should be modular and easy to manage individual components. Think of each component ideally can be turned off and on without detriment to other components.
