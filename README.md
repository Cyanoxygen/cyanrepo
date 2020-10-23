# CyanRepo

This is a third-party software repository built in personal interest, to provide some packages which are unavailable in the Official AOSC Tree.

Some of these packages are the proprietary release of a open source software, <!-- like Visual Studio Code --> some are fork of an open source software, and others are totally proprietary.

WARNING: This repo may against their EULAs. Use it at your own risk. Some packages are amd64 only.

## Usage

Add GPG Key to your APT keystore:

```

```

Then add an entry to your `sources.list`:

```

```

Then run `apt update`.

## Original idea

AOSC is a cool OS, but there's no support from some software vendors as they usually provide packages for Debian. 

So this idea comes out, to provide some (meta or not) packages in order to install these software in AOSC.


## List of packages

Hint: for "type" section, the definition is as follows:

- `O` stands for an open source software.
- `P` stands for an proprietary software, and no support other than specific distributions, and no universal prebuilt packages.
- `p` stands for an proprietary software, but they do provide an universal package (e.g. prebuilt tarballs).
- `V` stands for proprietary variant of an open source software, these are commonly "Official releases".
- `v` stands for fork of an open source software, they do have some features which are unavailable in the official tree.
- `a` stands for an prebuilt container format package from an open source software, such as AppImage.

| Done | Type | Package Name                   | Description                                                           | Source                                                                                      | Install path        | Available in |
| ---- | ---- | ------------------------------ | --------------------------------------------------------------------- | ------------------------------------------------------------------------------------------- | ------------------- | ------------ |
| Y    | `v`  | `qbittorrent-enhanced-edition` | qBittorrent Enhanced Edition, a qBittorrent fork, with many features. | https://github.com/c0re100/qBittorrent-Enhanced-Edition                                     | As is               | amd64, arm64 |
| Y    | `O`  | `libcurl-gnutls`               | cURL Library (GnuTLS flavour), with Debian naming.                    | https://github.com/archlinux/svntogit-community/blob/packages/libcurl-gnutls/trunk/PKGBUILD | As is               | amd64 only   |
| Y    | `P`  | `spotify-meta`                      | Meta package for installing Spotify software.                         | https://repository-origin.spotify.com/pool/non-free/s/spotify-client/                       | `/usr/lib/spotify/` | amd64 only   |
| Y    | `V`  | `vscode-vanilla-meta`               | The official release of Visual Studio Code, an powerful editor.       | https://go.microsoft.com/fwlink/?LinkID=620884                                              | `/usr/lib/vscode/`  | amd64, arm64 |
| N    | `P`  | `spotify`                      | Meta package for installing Spotify software.                         | https://repository-origin.spotify.com/pool/non-free/s/spotify-client/                       | `/usr/lib/spotify/` | amd64 only   |
| N    | `V`  | `vscode-vanilla`               | The official release of Visual Studio Code, an powerful editor.       | https://go.microsoft.com/fwlink/?LinkID=620884                                              | `/usr/lib/vscode/`  | amd64, arm64 |
| Y    | `O`  | `librespot`                    | An open source Spotify library                                        | https://github.com/librespot-org/librespot                                                  | As is               | amd64, arm64 |

<!--
| NEVER | `O` | `windowsnt-kernel` | Windows NT Kernel (5.1) | Unknown source | `file://C:/Windows/System32/` | amd64, i486 |
Just joking.
-->

## Manual packaging how-to, using Ciel

Feel free to build it yourself, it is not that hard though.

### Overall 

In summary build steps are basically as follows:

1. Install necessary build tools
2. Initialize build environment
3. Update the build environment
4. Clone tree
5. Build and install

You can learn more about packaging at [here](https://wiki.aosc.io/developer/packaging/basics/).

You have to do all these steps under AOSC OS, as this repo is oriented to AOSC itself. 

### Prepare build environment

Install `ciel` build tool:

```shell
sudo apt install ciel
```

Prepare a folder which Ciel will work at, e.g.

```shell
mkdir ~/ciel
cd ciel
```

### Initialize build environment

In the Ciel work directory, run:

NOTE: All Ciel commands should run in root.

```
sudo ciel init
```

And a Ciel workspace is created. Then we need to load a BuildKit in it:

Pick a mirror and download `aosc-os/os-{VARIANT}/buildkit/aosc-os_buildkit_latest_{VARIANT}.tar.xz` to any location (`VARIANT` is your platform, e.g. `amd64`, `arm64`):

```
wget https://repo.aosc.io/aosc-os/os-amd64/buildkit/aosc-os_buildkit_latest_amd64.tar.xz
```

Once downloaded, load the BuildKit into Ciel workspace:

```
sudo ciel load-os ./aosc-os_buildkit_latest_amd64.tar.xz
```

Once loaded, run `sudo ciel config -g` to configure your Ciel workspace. It will ask you whether to edit `sources.list`. This repository is targeted to Stable branch, so you should just modify the mirror link.

Once loaded and configured, you can now update your container:

```
sudo ciel update-os
```

### Initialize repo tree

In your Ciel workspace, you can now clone this tree into the `TREE` folder.

```
mkdir TREE
cd TREE
git clone https://github.com/Cyanoxygen/cyanrepo extra-cyanrepo
cd ..
```

Then you need a instance to actually run:

```
sudo ciel add stable
```

### Build it!

At this stage you are all set, and cleared to build your own package.

```
sudo ciel build -i stable <package1> <package2> ...
```

Once packages are built, you can find them under `OUTPUT/debs` folder.

Then it's your turn to install, run, or even host your own copy of this repository!

-----

## Having issue? Or requesting new package?

Just file an issue or make your own fork and make a pull request.

## Additional notes

Packages are removed if a package is sent to official ABBS Tree, built and published.

## Takedown notice

If you own one or more of the packages listed below, and you think this repository is against your EULA, ToS or other thing, please file an issue, and your package will be removed.


