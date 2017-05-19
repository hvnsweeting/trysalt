# Give SaltStack a try

SaltStack is a Python software to automate the management and configuration of
any infrastructure or application at scale.

More on https://docs.saltstack.com/

## Docker hub

[hvnsweeting/trysalt](https://hub.docker.com/r/hvnsweeting/trysalt/)

`latest` is latest version of Salt on Ubuntu 14.04

## Run

```
docker run -it hvnsweeting/trysalt
```

Try SaltStack remote execution, run:

```
salt-call --local  COMMAND # e.g salt-call --local network.interfaces
```

See more commands here
https://docs.saltstack.com/en/latest/topics/tutorials/modules.html

If you want to try `state.sls` or `state.apply`,
mount your states/formulas into /srv/salt/ and pillar in /srv/pillar

## Note
SaltStack does not suppose to run **on** Docker like other app services
(redis/jenkins/postgresql...). The image is mainly to give it a quick try,
easy the setting up problems.

SaltStack's main feature is managing service running, it works with underlying
`upstart`, `systemd`... but on Docker, those things does not normally exist.
Docker is created to run each process per container.
