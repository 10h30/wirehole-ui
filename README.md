### Quickstart
To get started all you need to do is clone the repository, modify the values noted below, and spin up the containers.

```
git clone git@github.com:OptimoSupreme/wirehole.git
cd wirehole
nano docker-compose.yml
```
Change `WG_HOST=my.ddns.net` to your server's public address, e.g. `WG_HOST=vpn.mydomain.com`.
> By default, any WireGuard client will have access to the Web UI, unless you set a password.
The Web UI will be available on http://0.0.0.0:51821. You can create new clients there.
