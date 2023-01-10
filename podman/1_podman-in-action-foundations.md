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

