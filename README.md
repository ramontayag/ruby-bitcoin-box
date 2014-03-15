Vagrant development box for Bitcoin Ruby projects:

- [bit_wallet](https://github.com/ramontayag/bitcoin_wallet)
- [bitsy](https://github.com/ramontayag/bitsy)
- [bitsy_client](https://github.com/ramontayag/bitsy_client-ruby)
- [ruby-bitcoin_testnet](https://github.com/ramontayag/ruby-bitcoin_testnet)

# Booting for the first time

Make sure you have the latest VirtualBox, Vagrant, and Ansible installed.

    vagrant up
    vagrant ssh

Paste your public key in vagrant's `~/.ssh/authorized_keys`. On your host, your public key is most likely `~/.ssh/id_rsa.pub`.

On the host, copy the following then tweak to your desire. For example, you may have other Vagrant machines that already use the default ip of `192.168.33.10` -- you can change that.

    cp config.yml{.sample,}
    cp development{.sample,}

    ansible-playbook development.yml -i development

## Troubleshooting

If you get this error while running `vagrant up`:

    [default] Configuring and enabling network interfaces...
    The following SSH command responded with a non-zero exit status.
    Vagrant assumes that this means the command failed!
    /sbin/ip addr flush dev eth1 2> /dev/null
    Stdout from the command:
    Stderr from the command:

then `vagrant ssh` into the VM and `sudo rm /etc/udev/rules.d/70-persistent-net.rules` as written [here](https://github.com/mitchellh/vagrant/issues/1351).

## BTC Love

If you find this useful, consider sharing some BTC love: `1PwQWijmJ39hWXk9X3CdAhEdExdkANEAPk`
