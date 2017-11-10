
# Synology

### Crashplan Pro

https://github.com/anveo/docker-crashplan

#### Docker

    $ docker pull anveo/crashplan:pro

    $ docker run \
      --detach \
      --name CrashPlan \
      --publish 4242:4242 \
      --publish 4243:4243 \
      --volume /volume1/crashplan:/var/crashplan \
      --volume /volume1:/storage \
      --volume /volume1:/volume1 \
      anveo/crashplan:pro

    $ ssh admin@ecto
    $ docker exec -it <container> cat /var/lib/crashplan/.ui_info; echo

On desktop:

    $ sudo vim "/Library/Application\ Support/CrashPlan/.ui_info"

Replace with output from above, adjust IP address to be address of the Synology server.
