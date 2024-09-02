---
title: "How to find out docker IP Address on ubuntu"
description: "how to easily retrieve the IP address of a running Docker container on Ubuntu using a simple Docker command."
date: "2024-09-02"
draft: false
---

When working with Docker containers, there may be times when you need to know the IP address of a running container, particularly for setting up network communication between containers or integrating with external services. On Ubuntu, this can be easily achieved using the following command:

```shell
docker inspect -f '{{range.NetworkSettings.Networks}}{{.IPAddress}}{{end}}' <ContainerName>
```

This command retrieves the IP address of a specified Docker container. It utilizes Docker's inspect functionality, which provides detailed information about Docker objects like containers, images, volumes, and networks. The -f option allows the output to be formatted using a Go template. In this example, the template iterates over all the networks associated with the container and extracts the IPAddress field from each network object.

To use this command, replace <ContainerName> with the actual name or ID of the container whose IP address you want to find. The command will then return the IP address associated with that container, allowing you to use it for further networking tasks.

This method is particularly useful in scenarios where containers need to communicate with each other or when services running outside of Docker require the container's IP address for integration. By programmatically accessing the container's IP address, you can streamline the process of configuring and managing Docker-based networks.
