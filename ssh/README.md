# SSH

### Allow TCP Forwarding

On remote computer:

    $ cat /etc/ssh/sshd_config
    ...
    Match User foobar
      AllowTcpForwarding yes
    ...

### Local Tunnel

Port `4200` is the local port, port `4300` is the remote.

    $ ssh -L 4200:localhost:4243 user@remote
