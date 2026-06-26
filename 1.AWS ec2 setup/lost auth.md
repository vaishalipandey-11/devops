BY generating new ssh key 
# SSH Key Authentication (AWS EC2)

1. Generate a new SSH key pair: `ssh-keygen -t ed25519 -f ~/.ssh/lvm_new_key`
2. `lvm_new_key` → Private Key (stays on your local machine, never share it).
3. `lvm_new_key.pub` → Public Key (copy this to the EC2 instance).
4. Add the public key to `~/.ssh/authorized_keys` on the EC2 instance.
5. Connect using: `ssh -i ~/.ssh/lvm_new_key ubuntu@<EC2_PUBLIC_IP>`
6. On first connection, type `yes` to trust the server's host key.
7. Server fingerprints are stored in `~/.ssh/known_hosts`.
8. Remove an old host key with: `ssh-keygen -R <EC2_PUBLIC_IP>`.
9. Debug SSH issues using: `ssh -vvv -i ~/.ssh/lvm_new_key ubuntu@<EC2_PUBLIC_IP>`.
10. Rule: **Private Key stays with you; Public Key goes to the server (`authorized_keys`).**