---
hide:
  - toc
title: engels74/tgraph-bot
---

[:octicons-mark-github-16: GitHub](https://github.com/engels74/tgraph-bot){ class="header-links" target="_blank" rel="noopener" }
[:octicons-container-16: ghcr.io](https://github.com/orgs/engels74/packages/container/package/tgraph-bot){ class="header-links" target="_blank" rel="noopener" }

[:octicons-link-16: Source Code](https://github.com/engels74/tgraph-bot-source){ class="header-links" target="_blank" rel="noopener" }

<div class="image-logo"><img src="/img/image-logos/tgraph-bot.svg" alt="logo"></div>

!!! question "What is this?"

    This is a Docker image for my [tgraph-bot](https://github.com/engels74/tgraph-bot-source). It posts Tautulli graphs to a Discord channel of your choice, with many more features.

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
<tr><td><div id="tag3881" onclick="CopyToClipboard('tag3881');return false;" class="tag-decoration">nightly</div><div id="tag13294" onclick="CopyToClipboard('tag13294');return false;" class="tag-decoration">nightly-87784dd6255bbf3da172777d78608a038965a542</div><div id="tag5000" onclick="CopyToClipboard('tag5000');return false;" class="tag-decoration">nightly-20f45ad</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/tgraph-bot/commit/20f45add586f3e930772ba8ade8978782740acd6" target="_blank">Upstream update: alpinevpn-337a82e => alpinevpn-4dcfd96</a></td><td><a href="https://github.com/engels74/tgraph-bot/actions/runs/20894187746" target="_blank">2026-01-11 11:12:12</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag30024" onclick="CopyToClipboard('tag30024');return false;" class="tag-decoration">latest</div><div id="tag8307" onclick="CopyToClipboard('tag8307');return false;" class="tag-decoration">release</div></td><td>Releases</td><td><a href="https://github.com/engels74/tgraph-bot/commit/0000000" target="_blank">Initial setup</a></td><td><a href="https://github.com/engels74/tgraph-bot/actions" target="_blank">2026-01-09 00:00:00</a></td></tr>
</tbody>
  </table>
</div>

## Starting the container

=== "cli"

    ```shell linenums="1"
    docker run --rm \
        --name tgraph-bot \
        -e PUID=1000 \
        -e PGID=1000 \
        -e UMASK=002 \
        -e TZ="Etc/UTC" \
        -v /<host_folder_config>:/config \
        ghcr.io/engels74/tgraph-bot
    ```

=== "compose"

    ```yaml linenums="1"
    services:
      tgraph-bot:
        container_name: tgraph-bot
        image: ghcr.io/engels74/tgraph-bot
        environment:
          - PUID=1000
          - PGID=1000
          - UMASK=002
          - TZ=Etc/UTC
        volumes:
          - /<host_folder_config>:/config
    ```

--8<-- "includes/wireguard.md"
