# Podman in Action - Foundations

## Podman: A next-generation container engine

> Topics:
>
> - What Podman is
> - The Advantage of using Podman over Docker
> - Examples of using Podman

### Why use Podman when you have Docker

Well one reason is that open source is all about choice. Operating systems have more than one editor, more than one shell, more than one filesystem, and more than one internet web browser.

The following paragraphs list some of Podman's most notable features compared to Docker.

#### Rootless containers

In many situations, you do not want to give full root access to your users, but users and developers still need to run containers and build container images.

Podman, on the other hand, can run containers with no additional security features in Linux other than a standard login account. With Podman the processes running on the system are always owned by the user and have no capabilities greater than a normal user. Even if you break out of the container, the process is still running as your UID, and all actions on the system are recorded in the audit logs. Users of Podman cannot simply remove the container and cover up their tracks.

> Note: Docker now has the ability to run rootless but this feature is not yet adopted by the general community.

#### Fork/exec model

Unix and C were designed with the fork/exec model of computing. Basically, when you execute a new program, a parent program like the Bash shell forks a new process and then executes the new program as a child of the old program.

| Docker client-server architecture                                 | Podman fork/exec architecture                                 |
|-------------------------------------------------------------------|---------------------------------------------------------------|
| ![Docker client-server architecture](img/docker_architecture.png) | ![Podman fork/exec architecture](img/podman_architecture.png) |

#### Daemonless

Podman can run all of the same container images as Docker and launch containers with the same container runtimes. However, Podman does this without having multiple continuously root-running daemons.

Your container will continue to run without the overhead of running the multiple daemons. Less overhead is incredibly popular on low-end machines like IOT devices and edge servers.

#### User-friendly command line

`alias Docher = Podman`: With this command, you can continue to type in your Docker commands, but Podman runs your containers. If the Podman command line differs from Docker, it is considered a bug in Podman, and users demand Podman to be fixed to make the tools match. The alias means when you type `docker ps`, the `podman ps` command runs.

Many distributions supply a package called podman-docker, which changes the alias from docker to podman and links the man page.

> Note: There are a few commands, such as Docker Swarm, that Podman doesn't support, but for the most part, Podman is a complete replacement for the Docker CLI.

#### Support for REST-API

Podman can be run as a socket-activated REST API service. This allows remote clients to manage and launch Podman containers. Podman supports the Docker API as well as the Podman API for advanced Podman features.

#### Integration with `systemd`

Podman wants to fully integrate the running of containers with the init system. Users want to use `systemd` to start and stop containers at boot time. Containers should do the following:

- Support `systemd` within a container
- Support socket activation
- Support `systemd` notifications that a containerized application is fully activated
- Allow `systemd` to fully manage the cgroups and lifespan of a containerized application

> Note: The upstream Docker community believes the Docker daemon, as opposed to systemd, should be the controller of processes, it should manage the life cycle of containers, and it should start and stop them at boot time.
