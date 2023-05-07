# my-torrent-fish

This is the source of my personal instance of [torrent-fish](https://github.com/tweedge/torrent-fish) - it helps people resolve magnet links to my torrents, in case there's nobody in the swarm currently.

> torrent-fish is a metadata-only BitTorrent peer built with libtorrent. It's designed to help keep magnet links which rely on [HTTP Seeding](https://wiki.vuze.com/w/HTTP_Seeding) healthy, without the overhead of running other peers or seeds.

Today, it's deployed on Google Cloud using the [free Compute Engine credits](https://cloud.google.com/free/docs/free-cloud-features#compute), which allows you to run a container seamlessly as if it were a regular instance using Google's COS image ([docs](https://cloud.google.com/compute/docs/containers/deploying-containers)). This is overkill for torrent-fish by a factor of about 10, but it's easy, and it's free.

Normally I *would* use Fly for deploying containers, Fly's network layer doesn't currently work well for torrent-fish given TCP and UDP need to be handled separately ([source](https://web.archive.org/web/20230507003741/https://fly.io/docs/app-guides/udp-and-tcp/)). They're working on it though - so this may move to Fly eventually.