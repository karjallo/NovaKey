# NovaKey

> [!NOTE]
> **Modernized Fork Notice:** I used this keyboard concept for many years, but it eventually became completely incompatible with modern Android versions. Since I don't have experience in mobile development and it wasn't a particular interest of mine, I vibe-coded an update to bring the code up to date so I could run it on my daily driver (Pixel 8a) and support current Android versions. Please note that for simplicity and to avoid extra maintenance work, the Wear OS wearable module has been disabled and is not functional at the moment.
>
> If you don't have enough developer experience to compile it yourself, you can download a pre-built APK from the [Releases page]({releases-link-apk}).
>
> * **Security Warning:** Running APKs compiled by someone else always carries inherent security risks. Only install binaries if you trust the source.
> * **Disclaimer:** This software is provided "as is", without warranty of any kind. I take no responsibility for any issues, data loss, or unexpected behavior resulting from its use.

> — karjallo



## An alternative input method.

The intent of NovaKey is to create an open platform for alternative input methods.
You are free to (and encouraged!) to contribute to this project with new languages, layouts, themes or whatever!

# Contribute
Everyone is encouraged to contribute to this project with ideas, code or designs
### Developers
If you would like to contribute to this project we ask you follow these simple steps:
1. If there isn't one already, make sure to add a new issue describing what you want to work on. This is to make sure there is no overlap with other contributions.
2. Once you have implemented your feature create a pull request referncing the issue number.
    e.g `[#002] Adds new French language layout`
### Designers
If you would like to contribute a design or an idea you can by submitting an issue to this repository labeled with `design request`. Or create a post in [our subreddit](https://www.reddit.com/r/NovaKey) tagged with [design request], someone will then create an issue in this repo to turn it into reality.

### Bugs
If you would like to report a bug or crash you can by submitting an issue to this repository labeled with `bug`. Or create a post in [our subreddit](https://www.reddit.com/r/NovaKey) tagged with [bug], someone will then create an issue in this repo in order to fix it.

# Architecture
At a high level NovaKey uses the [Model-View-Controller(MVC)](https://en.wikipedia.org/wiki/Model%E2%80%93view%E2%80%93controller) pattern. Taking a closer look though the logic is centered around `Elements` and `Actions`. The diagram below shows the architecture with more detail:

![architecturediagram](https://user-images.githubusercontent.com/13156162/51805618-c7af1380-223d-11e9-9eb9-55aeae3253df.png)

As shown by the diagram above `Elements` have three inputs and 2 outputs. `Elements` use the `User Input`, `State` & `Themes` to output to the `View` and to perform `Actions` which update the text & the `Model`.

This causes the app to behave like a [Finite State Machine](https://en.wikipedia.org/wiki/Finite-state_machine). For example, if the app is in the `Default` state and the user performs a shift action, the state will become `Shift`. Then if the user performs a shift action again the state will become `Caps Lock`.

# Licence

```
NovaKey - An alternative touchscreen input method
Copyright (C) 2019  Viviano Cantu

This program is free software: you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation, either version 3 of the License, or
(at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU General Public License for more details.

You should have received a copy of the GNU General Public License
along with this program.  If not, see <https://www.gnu.org/licenses/>

Any questions about the program or source may be directed to <strellastudios@gmail.com>
```
