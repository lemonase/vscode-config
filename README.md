# VS Code Settings

This repo is for my personal VS Code settings and configs.

## Docs

Defaults Settings (Reference):
https://code.visualstudio.com/docs/reference/default-settings

Default User Settings (File Location):
https://code.visualstudio.com/docs/configure/settings#_settings-file-locations

## Export Extensions List

```shell
code --list-extensions > extensions.txt
```

## Install Extensions

To install a single extension

```shell
code --install-extension <ext name>
```

Install from `extensions.txt` file:

```python
import subprocess

with open("extensions.txt") as f:
    for ext in f:
        subprocess.run(["code", "--install-extension", ext.strip()], shell=True)

```

## Install Settings

Clone this repo and moves it to the default settings location [here](https://code.visualstudio.com/docs/configure/settings#_settings-file-locations)
(dependent on platform).

```shell
# clone repo
git clone https://github.com/lemonase/vscode-config.git

# move to proper folder and delete repo
mv vscode-config/.git User/
rm -r vscode-config

# checkout/restore files
cd User/
git checkout .

# copy defaults (that way local customizations are not tracked)
cp keybindings.default.json keybindings.json
cp settings.default.json settings.json
```

## Why not the built in "Settings Sync"?

[Settings Sync](https://code.visualstudio.com/docs/configure/settings-sync) in
VS Code has wonky/buggy behavior and sometimes does not sync.
Not to mention you cannot comment on changes. There are also situations where I
want my VS Code config but I don't necessarily want to login and authenticate to
GitHub through VS Code.
