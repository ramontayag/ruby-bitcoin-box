Vagrant development box for Bitcoin Ruby projects:

- [bit_wallet](https://github.com/ramontayag/bitcoin_wallet)
- [bitsy](https://github.com/ramontayag/bitsy)
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
