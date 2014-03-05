Vagrant development box for Bitcoin Ruby projects:

- [bit_wallet](https://github.com/ramontayag/bitcoin_wallet)
- [bitsy](https://github.com/ramontayag/bitsy)
- [ruby-bitcoin_testnet](https://github.com/ramontayag/ruby-bitcoin_testnet)

# Booting for the first time

Make sure you have the latest VirtualBox, Vagrant, and Ansible installed.

    vagrant up
    vagrant ssh

Paste your public key (most likely `~/.ssh/id_rsa.pub`)

    ansible-playbook development.yml -i development
