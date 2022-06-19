# Nekogram iOS

## Features
(Coding......)

## Build

- Clone this repository with submodules:
```shell
git clone https://github.com/Surindaku/Nekogram-iOS.git --recursive
```

- Adjust configuration parameters

```
mkdir -p $HOME/telegram-configuration
cp -R build-system/example-configuration/* $HOME/telegram-configuration/
```

- Modify the values in `variables.bzl`
- Replace the provisioning profiles in `provisioning` with valid files

- Create a build cache directory to speed up rebuilds

```
mkdir -p "$HOME/telegram-bazel-cache"
```

- Generate the Xcode project and open it to build

```
python3 build-system/Make/Make.py \
    --cacheDir="$HOME/telegram-bazel-cache" \
    generateProject \
    --configurationPath="$HOME/telegram-configuration" \
    --disableExtensions
```

It is possible to generate a project that does not require any codesigning certificates to be installed: add `--disableProvisioningProfiles` flag:
```
python3 build-system/Make/Make.py \
    --cacheDir="$HOME/telegram-bazel-cache" \
    generateProject \
    --configurationPath="$HOME/telegram-configuration" \
    --disableExtensions \
    --disableProvisioningProfiles
```

## License
Apply Artistic License 2.0 for the additions under the premise of complying with GNU GPLv2.<br>
The Artistic License is based on GPL License and it requires that modified versions of the software do not prevent users from running [the standard version](https://github.com/TelegramMessenger/Telegram-iOS).
