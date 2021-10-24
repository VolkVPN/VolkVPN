# VolkVPN
VolksWagen did it with cars. **VolkVPN** is the VPN for the people

## The Idea
VPN providers offer dark and expensive services to be able to access the internet from other areas of the globe. VolkVPN is an open source project to automatically ramp up resources (e.g. VMs, containers, etc.) using the global infrastructure of public cloud providers (AWS, Azure and GCP). This provides very high performance for low cost, while you keep the flexibility of the expensive VPN providers.

## Concerns with current VPN providers
- VPN providers offer a service to make money, therefore adding a margin on top of the cost of the services
- As a tradicional business, they don't disclose what their logic do (source code), possibly being misused to track our behavior (re-selling our data?) or even worse, monitoring our internet use and data for cyber-intelligence purposes (e.g. intelligence agencies, APT hacking organizations, etc.).
- Free and cheap VPN alternatives provide very low performance. While it is not disclosed, you are most likely paying with your data (user-behavior, profiling for advertisement re-selling, etc.)

## How does VolkVPN work?
- Register with any of the public cloud providers (AWS, Azure and/or GCP). Get programmatic access keys.
- Install the cross-platform VolkVPN client
- Provide your credentials from the cloud provider (access keys, not username/password)
- Select the country/location where VolkVPN should ramp up resources. This is limited by the cloud provider(s) you configured VolkVPN to work with

## What we need to make VolkVPN a reality?
Client: A simple Electron application supporting Windows, Mac and Linux
- In the future mobile apps and a CLI could be possible, but for now not in scope
- We should be careful about how secrets are handled
- The client is in charge of handlind the complete infrastructure using Infrastructure as Code (Terraform?). It should automatically to destroy all resources when VolkVPN is not needed.
PoC with each of the cloud providers supported: AWS (focus for first release?), Azure and GCP
- We should check the EULA / usage conditions, maybe there is something against realizing VolkVPN
Resources used: VMs in the first iteration (Carlos: Concern with slow ramp-up times)
Documentation: Apart from a detailed technical documentation which allow other developers to contribute bugfixes and new features, we need also user documentation. The user documentation should be step-by-step, assuming no previous knowledge other than browsing the web lets say: "for dummies".
CI/CD pipeline: Targetting both unknown&known developers (test automation using cloud infrastructure), as well as regular users (one-click installer)
Cost comparison: VolkVPN should not be more expensive than (most) regular VPNs providers
Performance comparisons: VolkVPN should be way more stable and faster than (most) regular VPN providers
Project Management of the OSS project: Some kind of governance and so on, but this is only needed if the community grow
Publicity: With the first running version of the client, we should make some PRs (Press-Releases), marketing material, possibly a nice website (github site), etc.
