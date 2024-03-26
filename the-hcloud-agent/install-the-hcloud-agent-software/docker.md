# 🔥 Docker

The HCloud agent for Docker is a different beast. It is an agent in its own Docker container, based on Linux.

The HCloud Docker agent makes sense when you do not need a full workstation for a task, or when you want to automate tasks without user involvement.

Multiple Docker agents can share a host (e.g. in a server-based infrastructure) to serve as independent clients for different tasks in different organizations. You can take advantage of the options Docker offers to either isolate the agents, or share some resources for collaboration.

In this environments, a token has to be set for automated login after start or restart.
