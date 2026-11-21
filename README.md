# XaliFriends resource packs

**The GUI resource packs of XaliFriends**: the button icons, head models and
glyphs that draw the friend menus. There is one pack per place it can be installed. The release zips are what XaliFriends
downloads, so this repository is public and its releases carry nothing else.

## Packs

| Folder | Release zip | Goes |
|---|---|---|
| `vanilla` | `friends-gui-vanilla.zip` | A resource pack: host it and set it in `server.properties`, or send it from a plugin. |
| `nexo` | `friends-gui-nexo.zip` | Unpacked into `plugins/Nexo` (`items/`, `glyphs/`, `pack/`). |
| `itemsadder` | `friends-gui-itemsadder.zip` | Unpacked into `plugins/ItemsAdder` (`contents/friendsystem/`). |

Each zip has a `.sha256` beside it. XaliFriends installs the Nexo and ItemsAdder packs itself when `packs.handler` in its
`config.yml` is `nexo` or `itemsadder`: it reads the checksum from the
[latest release](https://github.com/Xalitoria/xali-friends-resourcepack/releases/latest) and downloads the zip only when it
changed. The vanilla pack is installed by hand.

## Building

The folders are the sources. XaliFriends builds the zips from them (`./gradlew :friends:resourcepack:zipPacks`, in the Xali
workspace), reproducibly, and its tests check that the three packs agree. The pack formats it supports are 84 to 97 (Minecraft
26.1 to 26.3).
