# Fundamentals of Containers

## Why containers

Containers are a powerful tool. They have had a tremendous impact on how we th industry does IT.

They help you to:

- Move faster
- Automate more
- Increase reliablility
- For less money

## What are containers

Containers are all about portable software. They are a technology that allows you to run software on a variety of systems, including a developer’s laptop,
all the way to a production system.

This speeds up deployment, simplifies automation, and ensures your code can run consistently in production, as well as everywhere else!

Like virtual machines, containers wrap your software in a standardized environment that allows it to run consistently on varied machines. But containers are smaller, use fewer resources, and are easier to automate than virtual machines.

## What is orchestration

Container Orchestration simply refers to processes used to manage containers and to automate the management of containers.
For example:

- I want to start up a set of five containers in production.
- I could spin up each container manually.
- Or, I could tell an orchestration tool like Kubernetes that I want five containers, and let the tool do it.

For the sake of redundancy, it’s a good idea to spin up my five containers on five different hosts.

The more complex my requirements for managing containers become, the more useful my orchestration tools become!

### Zero-downtime deployments

In the old days, deployments went like this:

1. Take the server down for maintenance (it is unavailable to customers).
2. Perform the deployment.
3. Bring the server back up.

A zero-downtime deployment (with containers) goes like this:

1. Spin up containers running the new code.
2. When they are fully up, direct user traffic to the new containers.
3. Remove the old containers running the old code. No downtime for users!

How do you coordinate those steps quickly and efficiently? Orchestration tools can do it for you!

## What are containers used for

This lesson is just a preview to get you thinking about how you might want to use containers. Check out the section on use cases for more details on how they can be used!

Containers are great at accomplishing things like:

- **Software Portability** – Running software consistently on different machines.
- **Isolation** – Keeping individual pieces of software separate from one another.
- **Scaling** – Increasing or decreasing resources allocated to software as needed.
- **Automation** – Automating processes to save time and money.
- **Efficient Resource Usage** – Containers use resources efficiently, which saves money.

## Advantages and limitations of containers

| Advantages | Limitations |
|------------|-------------|
| The isolation and portability of VMs. | Less flexibility than VMs – You can’t run a Windows container on a Linux machine (yet). |
| More lightweight then VMs - Less resource usage. | Introduces new challenges around orchestration and automation. |
| Faster than VMs – Containers can start up in seconds, not minutes. | |
| Smaller than VMs – Container images can be measured in megabytes, not gigabytes. | |
| All of these add up to faster and simpler automation! | |

## What is Docker

`Docker` is primarily a container runtime. This means that Docker is a piece of software that is designed to implement
and support containers.

At its core, Docker allows you to run containers on systems. It also offers a variety of tools for creating and managing containers and container images. It is currently the industry leader in container runtimes.

> Note: Check out the Docker official site for documentation and more info <https://www.docker.com/>

### Other container runtimes

- `rtl` Created by CoreOS, “designed with composability and security in mind.” <https://coreos.com/rkt/>
- `containerd` Emphasizes “simplicity, robustness, and portability.” <https://containerd.io/>

## Kubernetes

Kubernetes is a container orchestration tool. It allows you to easily build and manage your container infrastructure and
automation.

Do you want things like self-healing applications, automated scaling, and easy automated deployments? Then you should definitely look into Kubernetes!

> Note: Check out the official Kubernetes site for documentation and additional info <https://kubernetes.io/>
