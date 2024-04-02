# Docker

The helmut.cloud Agent for Docker is a different beast. It is an agent in its own Docker image, based on Linux.

The helmut.cloud Docker Agent makes sense when you want to run it on Linux and/or if you prefer to run it in a sandboxed environment.

Multiple Docker Agents can share a host (e.g. in a server-based infrastructure) to serve as independent Agents for different tasks in the same or different organizations. You can take advantage of the options Docker offers to either isolate the agents container, or share some resources for collaboration.

To download the helmut.cloud Docker Agent image, you can use our public repository: \`[ghcr.io/moovit-sp-gmbh/hcloud-agent:latest](https://ghcr.io/moovit-sp-gmbh/hcloud-agent:latest)'. You can find a list of available tags [here](https://github.com/orgs/moovit-sp-gmbh/packages/container/hcloud-agent/versions).
