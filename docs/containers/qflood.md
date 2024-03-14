---
hide:
  - toc
---

<div class="image-logo"><img src="/img/image-logos/flood.svg" alt="logo"></div>

--8<-- "includes/header-links.md"

!!! question "What is this?"

    This is a fork of Hotio's [rflood](https://hotio.dev/containers/rflood) Docker image, that uses qBittorrent instead of rtorrent. The qflood image currently only has "nightly support," which means it updates automatically after a successful run of [this workflow file](https://github.com/jesec/flood/actions/workflows/publish-rolling.yml). This means that whenever the official flood repository receives a push commit, this docker image should automatically be updated. All thanks to hotio's brilliant setup. The included [qBittorrent](https://github.com/userdocs/qbittorrent-nox-static) uses libtorrent v2.x.

???+ info "Why only nightly?"

    This docker image was created because, for whatever reason, jesec never seems to push an official release. And recent qBittorrent releases has [broken](https://github.com/jesec/flood/issues/629) hotio's old qflood image, which led him to [deprecate](https://discord.com/channels/610068305893523457/644100056244551680/1142642095950143598) the Docker image entirely. This fixes it, while also keeping the image updated. If a release of flood happens in the future, I might create an official `release` image as well. But for now, only the `nightly` image will be available.

## Starting the container

=== "cli"

    ```shell linenums="1"
    docker run --rm \
        --name qflood \
        -p 8080:8080 \
        -p 3000:3000 \
        -e PUID=1000 \
        -e PGID=1000 \
        -e UMASK=002 \
        -e TZ="Etc/UTC" \
        -e FLOOD_AUTH="true" \
        -e ARGS="" \
        -e FLOOD_ARGS="" \
        -v /<host_folder_config>:/config \
        -v /<host_folder_data>:/data \
        --restart unless-stopped \
        ghcr.io/engels74/qflood
    ```

=== "compose"

    ```yaml linenums="1"
    version: "3.7"

    services:
      qflood:
        container_name: qflood
        image: ghcr.io/engels74/qflood
        ports:
          - "8080:8080"
          - "3000:3000"
        environment:
          - PUID=1000
          - PGID=1000
          - UMASK=002
          - TZ=Etc/UTC
          - FLOOD_AUTH=true
          - ARGS
          - FLOOD_ARGS
        volumes:
          - /<host_folder_config>:/config
          - /<host_folder_data>:/data
        restart: unless-stopped
    ```

--8<-- "includes/tags.md"

## Changing the WebUI port

Under certain circumstances it's required to run the WebUI on a different internal port, you can do that by modifying the environment variable `WEBUI_PORTS` accordingly. It should be in the format `xxxx/tcp,xxxx/udp`, take a look at the default with `docker logs` (variable is printed at container start) or `docker inspect`.

--8<-- "includes/wireguard.md"
