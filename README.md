#Microservices with Golang

## Microservices ;TLDR

- Complex application built with small independent services
- Communicate with each other via language-agnostic APIs
- Each services is responsible for a single task
- Can be independently built, tested, and deployed
- Modern take on SOA ( minus the COBRA, SOAP, & XML )

## Golang <3 Microservices

- Unix Philosophy complements Microservices architectures
- Simplicity of language encourages single purpose applications
- Standard library makes networking trivial
- No runtime dependencies and single binary deployable

## Code Organization

- Keep it flat until you need structure
- Share functionality via internal services
- When needed make internal service public facing via proxy
- Avoid a hairball, don't go more then 2 layers deep

## Networking

- Good | REST APIs using JSON
- Good | RPC via Binary protocols
- Good | Messages passing via unified log or message queues
- Bad | XML RPC
- Bad | REST APIs using XML
- Use load balancers to create fault tolerant resource pools

## Building

- 1 repo per type of service
- Even if code is shared avoid monolithic service
- Build can result in one or more binaries
- Push binaries to a centerialized repo 

## Deploying

- Keep the build and deployment processes decoupled
- Pull deployable from binary repo
- Binary should get it's config from env vars
- Deployment biss with no runtime dependencies
- Don't need containers but works fine if that's your deployment method
