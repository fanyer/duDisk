Space Radar Electron
====
Space Radar Electron is a space visualizer that allows interactive Sunburst and Treemap charting of your disk space and memory.

![](https://pbs.twimg.com/media/CRi_IYuU8AAhobo.png:large)

This project started as quick prototype for me to test drive [atom electron](http://electron.atom.io) (some es6 syntax), [d3.js](https://d3js.org) and for me to explore the question of "what's taking up my disk space". Turns out writing a disk visualization app isn't that simple as I dwell into figuring out how to make disk scanning not block the ui thread, ipc calls go faster, smoother rendering, lesser memory usage, more sensible interactions...

Downloads
==
Download Mac and Windows at the [releases page](https://github.com/zz85/space-radar-electron/releases)

Features
==
- previews visualization as disk is being scanned
- cross platform (at least on Mac OS X and Windows)
- allow drilldown of directories
- breadcrumbs and navigation

Future Enhancements
==
- more target for scanning
- color by file types
- filter hidden files
- moar!!
- let me know what you think

Futher Explorations
==
- More efficient memory usage
- More efficient scanning process
- 3D visualization

Whats New
==
V4
- Treemap view
- Memory monitoring
- Mac App look using [Photon](http://photonkit.com)
- Context Menus for locating + opening + deleting files / directories
- Navigation controls (back/fwd/up)
- Switched disk scanning jobs to invisible renderer process

Version 3
- App icon finally! Thanks [Jill](http://jilln.com/) for the help with this :)
- Many Bug fixes
- Disk scanning is moved to a webview process
- Investigated various RPC methods. Now uses LocalStorage + FileSystem IPC message passing
- Reduce memory usage (and Electron crashes) by not caching key paths
- Tested on > 100GB & 2M files
- Improvements to user interactivity esp on hover states
- To prevent renderer process from hitting heap mem limit (1.5GB), all previous data is null, with dom elements removed to reduce memory pressure
- Allow target selection for disk usage scanning
- Locate path in Finder
- Env Debug Flags

Version 2
- Major speed up scanning directories. About 10x from version 1, and almost as fast or faster than du.
- Runs disk scanning as a separate headless renderer process
- Json is passed back via IPC
- Remove Async npm dependency

Issues
==
Please raise on [github issue tracker](https://github.com/zz85/space-radar-electron/issues) or contact [@blurspline on twitter](http://twitter.com/blurspline)

Development
==

Run

```
DEBUG=true electron .
```

or

```
npm run app
```

Check that you have depdencies installed, otherwise run (this may take awhile for electron binaries)

```
npm install
```

Thanks
==
- [Jill](http://jilln.com/) for designing the app logo
- Jianwei for his comments on the app
- Chee Aun for helping alpha test the app
- WM for his talk on Electron that got me started