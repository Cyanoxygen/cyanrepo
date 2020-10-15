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

Then run `apt-update`.

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
| Y    | `P`  | `spotify`                      | Meta package for installing Spotify software.                         | https://repository-origin.spotify.com/pool/non-free/s/spotify-client/                       | `/usr/lib/spotify/` | amd64 only   |
| Y    | `V`  | `vscode-vanilla`               | The official release of Visual Studio Code, an powerful editor.       | https://go.microsoft.com/fwlink/?LinkID=620884                                              | `/usr/lib/vscode/`  | amd64, arm64 |
| N    | `O`  | `librespot`                    | An open source Spotify library                                        | https://github.com/librespot-org/librespot                                                  | As is               | amd64, arm64 |

<!--
| NEVER | `O` | `windowsnt-kernel` | Windows NT Kernel (5.1) | Unknown source | `file://C:/Windows/System32/` | amd64, i486 |
Just joking.
-->

## Having issue? Or requesting new package?

Just file an issue or make your own fork and make a pull request.

## Additional notes

Packages are removed if a package is sent to official ABBS Tree, built and published.

## Takedown notice

If you own one or more of the packages listed below, and you think this repository is against your EULA, ToS or other thing, please file an issue, and your package will be removed.


