---
hide:
  - toc
title: engels74/base-image
---

[:octicons-mark-github-16: GitHub](https://github.com/engels74/base-image){ class="header-links" target="_blank" rel="noopener" }
[:octicons-container-16: ghcr.io](https://github.com/orgs/engels74/packages/container/package/base-image){ class="header-links" target="_blank" rel="noopener" }

[:octicons-link-16: Upstream Project](https://github.com/hotio/base){ class="header-links" target="_blank" rel="noopener" }

<div class="image-logo"><img src="/img/image-logos/base-image.svg" alt="logo"></div>

!!! question "What is this?"

    This is a fork of Hotio's Docker image. It's used for my other Docker images. It's basically the same as Hotio's except that it's tailored to my containers.

<div id="tags-table">
  <table>
    <thead>
      <tr>
        <th>Tags <span class="twemoji" title="Click Tag to Copy"><svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24"><path d="M11 9h2V7h-2m1 13c-4.41 0-8-3.59-8-8s3.59-8 8-8 8 3.59 8 8-3.59 8-8 8m0-18A10 10 0 0 0 2 12a10 10 0 0 0 10 10 10 10 0 0 0 10-10A10 10 0 0 0 12 2m-1 15h2v-6h-2z"></path></svg></span></th>
        <th>Description</th>
        <th>Commit</th>
        <th>Last Updated</th>
      </tr>
    </thead>
    <tbody id="tags-table-body">
<tr><td><div id="tag4576" onclick="CopyToClipboard('tag4576');return false;" class="tag-decoration">alpinevpn</div><div id="tag4735" onclick="CopyToClipboard('tag4735');return false;" class="tag-decoration">alpinevpn-4dcfd96</div></td><td>Alpine 3.22</td><td><a href="https://github.com/engels74/base-image/commit/4dcfd966e99fffda4ffd0dd0865236c35251a742" target="_blank">Sync with upstream (hotio/base@alpinevpn) and apply custom updates</a></td><td><a href="https://github.com/engels74/base-image/actions/runs/20893711281" target="_blank">2026-01-11 10:32:43</a></td></tr>
<tr><td><div id="tag12096" onclick="CopyToClipboard('tag12096');return false;" class="tag-decoration">noblevpn</div><div id="tag7885" onclick="CopyToClipboard('tag7885');return false;" class="tag-decoration">noblevpn-021c676</div></td><td>Ubuntu 24.04</td><td><a href="https://github.com/engels74/base-image/commit/021c67670138bb6f9c9b6cd082d561fcba8152b4" target="_blank">Sync with upstream (hotio/base@noblevpn) and apply custom updates</a></td><td><a href="https://github.com/engels74/base-image/actions/runs/20857578382" target="_blank">2026-01-09 15:57:39</a></td></tr>
</tbody>
  </table>
</div>

## Starting the container

=== "cli"

    ```shell linenums="1"
    docker run --rm \
        --name base-image \
        -e PUID=1000 \
        -e PGID=1000 \
        -e UMASK=002 \
        -e TZ="Etc/UTC" \
        -v /<host_folder_config>:/config \
        ghcr.io/engels74/base-image:alpinevpn
    ```

=== "compose"

    ```yaml linenums="1"
    services:
      base-image:
        container_name: base-image
        image: ghcr.io/engels74/base-image:alpinevpn
        environment:
          - PUID=1000
          - PGID=1000
          - UMASK=002
          - TZ=Etc/UTC
        volumes:
          - /<host_folder_config>:/config
    ```

This image is the base-image image for all other application images, however it can be used as a standalone VPN image for other images to attach to.

--8<-- "includes/wireguard.md"
