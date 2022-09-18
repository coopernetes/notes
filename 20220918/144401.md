# 144401
Including other gitconfig files:

```shell
git config --file $HOME/.config/git/addl-config user.signingkey <machine-specific-gpg-key>
git config --global include.path=.config/git/addl-config # relative to $HOME
git config -l --includes 				 # git config recognizes and combines settings from includes
```

