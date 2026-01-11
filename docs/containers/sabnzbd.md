---
hide:
  - toc
title: engels74/sabnzbd
---

[:octicons-mark-github-16: GitHub](https://github.com/engels74/sabnzbd){ class="header-links" target="_blank" rel="noopener" }
[:octicons-container-16: ghcr.io](https://github.com/orgs/engels74/packages/container/package/sabnzbd){ class="header-links" target="_blank" rel="noopener" }

[:octicons-link-16: Upstream Project](https://sabnzbd.org){ class="header-links" target="_blank" rel="noopener" }

<div class="image-logo"><img src="/img/image-logos/sabnzbd.svg" alt="logo"></div>

!!! question "What is this?"

    This is a fork of Hotio's [SABnzbd](https://hotio.dev/containers/sabnzbd) Docker image, that includes ffprobe, at `/app/bin/ffprobe`. Useful for scripts.

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
<tr><td><div id="tag1159" onclick="CopyToClipboard('tag1159');return false;" class="tag-decoration">nightly</div><div id="tag24689" onclick="CopyToClipboard('tag24689');return false;" class="tag-decoration">nightly-df1c0915d07982546e282b2b52354a49cde993ba</div><div id="tag28941" onclick="CopyToClipboard('tag28941');return false;" class="tag-decoration">nightly-b5b5116</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/b5b5116a05b9625020b73d6065e71d821a1143a6" target="_blank">Upstream update: alpinevpn-337a82e => alpinevpn-4dcfd96</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/20894187324" target="_blank">2026-01-11 11:12:09</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag263" onclick="CopyToClipboard('tag263');return false;" class="tag-decoration">release</div><div id="tag13381" onclick="CopyToClipboard('tag13381');return false;" class="tag-decoration">release-4.5.5</div><div id="tag29732" onclick="CopyToClipboard('tag29732');return false;" class="tag-decoration">release-6f77460</div><div id="tag15170" onclick="CopyToClipboard('tag15170');return false;" class="tag-decoration">release-v4</div><div id="tag20579" onclick="CopyToClipboard('tag20579');return false;" class="tag-decoration">release-v4.5</div><div id="tag5024" onclick="CopyToClipboard('tag5024');return false;" class="tag-decoration">release-v4.5.5</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/6f774602c88be65478108a5113c18473b3a7b2c5" target="_blank">Upstream update: alpinevpn-337a82e => alpinevpn-4dcfd96</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/20894187466" target="_blank">2026-01-11 11:12:10</a></td></tr>
<tr><td><div id="tag20748" onclick="CopyToClipboard('tag20748');return false;" class="tag-decoration">testing</div><div id="tag14730" onclick="CopyToClipboard('tag14730');return false;" class="tag-decoration">testing-4.6.0Beta2</div><div id="tag18529" onclick="CopyToClipboard('tag18529');return false;" class="tag-decoration">testing-70bc6be</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/70bc6beff3c698af968ab0cdbf4b85d0abb43dca" target="_blank">Upstream update: alpinevpn-337a82e => alpinevpn-4dcfd96</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/20894187511" target="_blank">2026-01-11 11:12:11</a></td></tr>
</tbody>
  </table>
</div>

## Starting the container

=== "cli"

    ```shell linenums="1"
    docker run --rm \
        --name sabnzbd \
        -p 8080:8080 \
        -e PUID=1000 \
        -e PGID=1000 \
        -e UMASK=002 \
        -e WEBUI_PORTS="8080/tcp,8080/udp" \
        -e ARGS="" \
        -e TZ="Etc/UTC" \
        -v /<host_folder_config>:/config \
        -v /<host_folder_data>:/data \
        ghcr.io/engels74/sabnzbd
    ```

=== "compose"

    ```yaml linenums="1"
    services:
      sabnzbd:
        container_name: sabnzbd
        image: ghcr.io/engels74/sabnzbd
        ports:
          - "8080:8080"
        environment:
          - PUID=1000
          - PGID=1000
          - UMASK=002
          - TZ=Etc/UTC
          - WEBUI_PORTS=8080/tcp,8080/udp
          - ARGS
        volumes:
          - /<host_folder_config>:/config
          - /<host_folder_data>:/data
    ```

--8<-- "includes/wireguard.md"
