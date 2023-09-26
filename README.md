# AVD and CVaaS Provisioning Demo

## How to Run the Demo

> **WARNING**: A CVaaS instance is required to run this demo.

The lab network can be created using Containerlab inside the provided Dev Container.  
The Dev Container can be started on any machine with Docker using [supporting tool](https://containers.dev/supporting) (for example [VSCode](https://code.visualstudio.com/)) or as a [Codespace](https://github.com/features/codespaces) on forked Github repository.

Before you start the Dev Container, you must set following environment variables on your system:

- ARTOKEN - token required to download cEOS image from [arista.com](https://www.arista.com/). You can find it in your arista.com profile settings if it's enabled for your account.
- CVTOKEN - CVaaS streaming token. This token must be created in advance and remain valid during the demo runtime.
- CV_API_TOKEN - CVaaS API token. This token must be created in advance and remain valid during the demo runtime.

> **NOTE**: When using Github Codespaces, these variables must be set in `Settings > Secrets and variables > Codespaces`

## Security Considerations

> **WARNING**: Make sure that nobody else has access to your Codespace / Container and that it is destroyed after the demo as environment variables will be cached in the container memory.
