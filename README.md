# CyanRepo

This is a thirc-party software repository built in personal interest, to provide some unavailable packages in the Official AOSC Tree.

Some packages are the proprietary version of a open source software, <!-- like Visual Studio Code --> some are fork of an open source software, and others are totally proprietary.

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

Hint: for "type" sectioin, the definition is as follows:

- `O` stands for an open source software.
- `P` stands for an proprietary software, and no support other than specific distributions, and no universal prebuilt packages.
- `p` stands for an proprietary software, but they do provide an universal package (e.g. prebuiut tarballs).
- `V` stands for proprietary variant of an open source software, these are commonly "Official releases".
- `v` stands for fork of an open source software, they do have some features which are unavailable in the official tree.
- `a` stands for an prebuilt container format package from an open source software, such as AppImage.

| Done | Type | Package Name                   | Description                                                                                                                                                     | Source                                                                | Install path        | Available in |
| ---- | ---- | ------------------------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------- | ------------------- | ------------ |
| Y    | `v`  | `qbittorrent-enhanced-edition` | qBittorrent Enhanced Edition, a powerful Bittorrent software clone, with many features.                                                                         | https://github.com/c0re100/qBittorrent-Enhanced-Edition               | As is               | amd64, arm64 |
| Y    | `P`  | `spotify`                      | Meta package for installing Spotify software. WARNING: local files playback is currently not supported. You may receive segfault after clicking "Add a source". | https://repository-origin.spotify.com/pool/non-free/s/spotify-client/ | `/usr/lib/spotify/` | amd64 only   |
| N    | `V`  | `vscode-vanilla`               | The official release of Visual Studio Code, an powerful editor.                                                                                                 | https://go.microsoft.com/fwlink/?LinkID=620884                        | `/usr/lib/vscode/`  | amd64, arm64 |


## New package request

Just file an issue or make your own fork and make a pull request.

## Additional notes

Packages are removed if a package is sent to official ABBS Tree, built and published.

## Takedown notice

If you own one or more of the packages listed below, and you think this repository is against your EULA, ToS or other thing, please file an issue, and your package will be removed.


