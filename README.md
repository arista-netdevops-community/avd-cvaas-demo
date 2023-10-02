# AVD and CVaaS Provisioning Demo

To access the slides, please use the following links:

- [Web Slides (Recommended)](https://arista-netdevops-community.github.io/avd-cvaas-demo/)
- [PDF Slides](https://github.com/arista-netdevops-community/avd-cvaas-demo/blob/gh-pages/avd_extended_workshop.pdf)

## How to Run the Demo

> **WARNING**: A CVaaS instance is required to run this demo.

The lab network can be created using Containerlab inside the provided Dev Container.  
The Dev Container can be started on any machine with Docker using [supporting tool](https://containers.dev/supporting) (for example [VSCode](https://code.visualstudio.com/)) or as a [Codespace](https://github.com/features/codespaces) on forked Github repository.

Before you start the Dev Container, you must set following environment variables on your system:

- ARTOKEN - token required to download cEOS image from [arista.com](https://www.arista.com/). You can find it in your arista.com profile settings if it's enabled for your account.
- CVURL - the url to be used to contact the CVaaS instance. For example: `www.cv-staging.corp.arista.io`
- CVUSER - for CVaaS token based authentication the username must be `cvaas`. `cvaas` is the default value if the variable is not set.
- CVTOKEN - CVaaS streaming token. This token must be created in advance and remain valid during the demo runtime.
- CV_API_TOKEN - CVaaS API token. This token must be created in advance and remain valid during the demo runtime.

> **NOTE**: When using Github Codespaces, these variables must be set in `Settings > Secrets and variables > Codespaces`

## Security Considerations

> **WARNING**: Make sure that nobody else has access to your Codespace / Container and that it is destroyed after the demo as environment variables will be cached in the container memory.
