```
git clone --bare git@github.com:lbernick/dotfiles.git $HOME/.dotfiles
```
## SSH stuff

- Make sure ssh agent is running locally:
  - Start the agent if it isn't already running: `eval "$(ssh-agent -s)"`
  - Add private key to the agent `ssh-add ~/.ssh/path_to_key`
  - Verify: ssh-add -l
- Add `ForwardAgent yes` to host in `~/.ssh/config` locally
- On host, set `AllowAgentForwarding yes` in /etc/ssh/sshd_config
  - unsure if actually necessary (?)
- Check if agent is being forwarded: `echo $SSH_AUTH_SOCK` (on host)
- Check that I can connect to github from host: `ssh -T git@github.com`
