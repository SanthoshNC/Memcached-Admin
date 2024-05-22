# Memcached Admin 

![Docker Image Size (latest by date)](https://img.shields.io/docker/image-size/hatamiarash7/memcached-admin) ![Docker Cloud Build Status](https://img.shields.io/docker/cloud/build/hatamiarash7/memcached-admin) [![Docker Image CI](https://github.com/hatamiarash7/Memcached-Admin/actions/workflows/docker-image.yml/badge.svg)](https://github.com/hatamiarash7/Memcached-Admin/actions/workflows/docker-image.yml) [![Publish Image](https://github.com/hatamiarash7/Memcached-Admin/actions/workflows/docker-publish.yml/badge.svg)](https://github.com/hatamiarash7/Memcached-Admin/actions/workflows/docker-publish.yml)

This program allows to see in **real-time** (top-like) or from the start of the server, **stats for get, set, delete, increment, decrement, evictions, reclaimed, cas command**, as well as **server stats** (network, items, server version) with google charts and **server internal configuration**

You can go further to **see each server slabs, occupation, memory wasted and items** (**key & value**).

Another part can execute commands to any memcached server : get, set, delete, flush_all, as well as execute any commands (like stats) with telnet

![image](app.png)

## Statistics

- Stats for each or all memcached servers, items, evicted, reclaimed ...
- Stats for every command : set, get, delete, incr, decr, cas ...
- Slabs stats (Memory, pages, memory wasted, items)
- Items stats (View items in slabs, then data for each key)
- Network stats (Traffic, bandwidth)

## Commands

- Execute commands : get, set, delete, flush_all on servers to administrate or debug it
- Get data with key on servers
- Delete keys on servers
- Flush servers
- Execute telnet command directly from phpMemcachedAdmin
- Search for specific pattern into all keys

## Live Stats

- Top-like real time stats with configurable alerts

## Configuration

- Edit configuration directly from web page
- phpMemcachedAdmin can use socket communication, PECL Memcache or Memcached API
- Organize your servers into cluster

---

### Install

#### Single server setup

Environments :

- **MEMCACHED_HOST** : Default address of the server
- **MEMCACHED_PORT** : Default port of the server

```shell
docker run --rm -p 8080:80 -e MEMCACHED_HOST='127.0.0.1' -e MEMCACHED_PORT='11211' hatamiarash7/memcached-admin:master
```

#### Multiple server setup (using the `Default` cluster)

Environments :

- **MEMCACHED_HOST** : Comma separated hostname and optional port
- **MEMCACHED_PORT** : Default port of the hostnames not having a port specified

```shell
docker run --rm -p 8080:80 -e MEMCACHED_HOST='127.0.0.1:11211,127.0.0.1:11212' hatamiarash7/memcached-admin:master
# or
docker run --rm -p 8080:80 -e MEMCACHED_HOST='127.0.0.1,127.0.0.2' -e MEMCACHED_PORT='11211' hatamiarash7/memcached-admin:master
# or
docker run --rm -p 8080:80 -e MEMCACHED_HOST='127.0.0.1:11212,127.0.0.1' -e MEMCACHED_PORT='11211' hatamiarash7/memcached-admin:master
```

You can define your cluster in **Configuration** section

### Test

We have a `docker-compose.yml` file here for testing purpose. You can run it with the following command:

```bash
docker compose up -d
```

Open your browser and go to http://localhost:8085/index.php?server=memcached:11211 to see the dashboard.

---

## Support

[![Donate with Bitcoin](https://en.cryptobadges.io/badge/micro/3GhT2ABRuHuXGNzP6DH5KvLZRTXCBKkx2y)](https://en.cryptobadges.io/donate/3GhT2ABRuHuXGNzP6DH5KvLZRTXCBKkx2y) [![Donate with Ethereum](https://en.cryptobadges.io/badge/micro/0x4832fd8e2cfade141dc4873cc00cf77de604edde)](https://en.cryptobadges.io/donate/0x4832fd8e2cfade141dc4873cc00cf77de604edde)

[![ko-fi](https://www.ko-fi.com/img/githubbutton_sm.svg)](https://ko-fi.com/D1D1WGU9)

<div><a href="https://payping.ir/@hatamiarash7"><img src="https://cdn.payping.ir/statics/Payping-logo/Trust/blue.svg" height="128" width="128"></a></div>

## Contributing

Don't be shy to be a contributor 😉

1. Fork it !
2. Create your feature branch : `git checkout -b my-new-feature`
3. Commit your changes : `git commit -am 'Add some feature'`
4. Push to the branch : `git push origin my-new-feature`
5. Submit a pull request

## Issues

Each project may have many problems. Contributing to the better development of this project by reporting them.
