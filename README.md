# VS Code Settings

This repo is for my personal VS Code settings and configs.

## Docs

Defaults Settings (Reference):
https://code.visualstudio.com/docs/reference/default-settings

Default Settings (Location):
https://code.visualstudio.com/docs/configure/settings#_profile-settings

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

Clone this repo to the default settings location [here](https://code.visualstudio.com/docs/configure/settings#_profile-settings)
(dependent on platform).
