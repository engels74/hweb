---
hide:
  - toc
title: engels74/qbittorrent
---

[:octicons-mark-github-16: GitHub](https://github.com/engels74/qbittorrent){ class="header-links" target="_blank" rel="noopener" }
[:octicons-container-16: ghcr.io](https://github.com/orgs/engels74/packages/container/package/qbittorrent){ class="header-links" target="_blank" rel="noopener" }

[:octicons-link-16: Upstream Project](https://github.com/qbittorrent/qbittorrent){ class="header-links" target="_blank" rel="noopener" }

<div class="image-logo"><img src="/img/image-logos/qbittorrent.svg" alt="logo"></div>

!!! question "What is this?"

    This is a fork of Hotio's [qBittorrent](https://hotio.dev/containers/qbittorrent) Docker image, that uses [libtorrent v2.x](https://github.com/userdocs/qbittorrent-nox-static/releases) by default.

    Hotio [recently](https://github.com/hotio/qbittorrent/commit/e8dada05befebf51d73669a05b09ef046c6f69e6) added the option to define by ENV if you want to use libtorrent v1 or v2. This one uses `v2` by default.

    This also still includes VueTorrent in the image, as hotio also removed support for themes.

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
<tr><td><div id="tag14830" onclick="CopyToClipboard('tag14830');return false;" class="tag-decoration">legacy</div><div id="tag9437" onclick="CopyToClipboard('tag9437');return false;" class="tag-decoration">legacy-4.3.9</div><div id="tag12056" onclick="CopyToClipboard('tag12056');return false;" class="tag-decoration">legacy-50678ba</div><div id="tag16295" onclick="CopyToClipboard('tag16295');return false;" class="tag-decoration">legacy-v4</div><div id="tag18379" onclick="CopyToClipboard('tag18379');return false;" class="tag-decoration">legacy-v4.3</div><div id="tag7565" onclick="CopyToClipboard('tag7565');return false;" class="tag-decoration">legacy-v4.3.9</div></td><td>Fixed to v4.3.9</td><td><a href="https://github.com/engels74/qbittorrent/commit/50678ba848ff86d43538fc9e76d322f78f924d2d" target="_blank">Upstream update: alpinevpn-337a82e => alpinevpn-4dcfd96</a></td><td><a href="https://github.com/engels74/qbittorrent/actions/runs/20894186502" target="_blank">2026-01-11 11:12:05</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag27291" onclick="CopyToClipboard('tag27291');return false;" class="tag-decoration">release</div><div id="tag12497" onclick="CopyToClipboard('tag12497');return false;" class="tag-decoration">release-5.1.4</div><div id="tag10559" onclick="CopyToClipboard('tag10559');return false;" class="tag-decoration">release-dac921c</div><div id="tag20458" onclick="CopyToClipboard('tag20458');return false;" class="tag-decoration">release-v5</div><div id="tag10270" onclick="CopyToClipboard('tag10270');return false;" class="tag-decoration">release-v5.1</div><div id="tag7310" onclick="CopyToClipboard('tag7310');return false;" class="tag-decoration">release-v5.1.4</div></td><td>Releases</td><td><a href="https://github.com/engels74/qbittorrent/commit/dac921cfac528ea1aba31093a4a6d29848c737c4" target="_blank">Upstream update: alpinevpn-337a82e => alpinevpn-4dcfd96</a></td><td><a href="https://github.com/engels74/qbittorrent/actions/runs/20894186752" target="_blank">2026-01-11 11:12:06</a></td></tr>
</tbody>
  </table>
</div>

## Starting the container

=== "cli"

    ```shell linenums="1"
    docker run --rm \
        --name qbittorrent \
        -p 8080:8080 \
        -e PUID=1000 \
        -e PGID=1000 \
        -e UMASK=002 \
        -e TZ="Etc/UTC" \
        -e WEBUI_PORTS="8080/tcp,8080/udp" \
        -e LIBTORRENT="v2" \
        -v /<host_folder_config>:/config \
        -v /<host_folder_data>:/data \
        ghcr.io/engels74/qbittorrent
    ```

=== "compose"

    ```yaml linenums="1"
    services:
      qbittorrent:
        container_name: qbittorrent
        image: ghcr.io/engels74/qbittorrent
        ports:
          - "8080:8080"
        environment:
          - PUID=1000
          - PGID=1000
          - UMASK=002
          - TZ=Etc/UTC
          - WEBUI_PORTS=8080/tcp,8080/udp
          - LIBTORRENT=v2
        volumes:
          - /<host_folder_config>:/config
          - /<host_folder_data>:/data
    ```

## Alternative Web UI

This image comes bundled with the alternative Web UI [VueTorrent](https://github.com/VueTorrent/VueTorrent) (`/app/vuetorrent`). Nightwalker is removed, as it is no longer maintained.

--8<-- "includes/wireguard.md"
