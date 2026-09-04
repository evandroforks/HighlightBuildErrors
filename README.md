Highlight Build Errors
======================

A plugin for [Sublime Text 3](http://www.sublimetext.com/) that highlights the lines that caused errors in the build.

![Screen capture with the Monokai theme](http://i.imgur.com/nj4WGFF.png)

## Feature

* Does only one thing: highlights the erroneous lines after a build
* Highlights are visible in the mini-map
* Customizable display (fill, outline, underline, icon...)
* Works fine with [Better Build System](https://sublime.wbond.net/packages/Better%20Build%20System)


## Installation

### By Package Control

1. Download & Install **`Sublime Text 3`** (https://www.sublimetext.com/3)
1. Go to the menu **`Tools -> Install Package Control`**, then,
    wait few seconds until the installation finishes up
1. Now,
    Go to the menu **`Preferences -> Package Control`**
1. Type **`Add Channel`** on the opened quick panel and press <kbd>Enter</kbd>
1. Then,
    input the following address and press <kbd>Enter</kbd>
    ```
    https://raw.githubusercontent.com/evandrocoan/StudioChannel/master/channel.json
    ```
1. Go to the menu **`Tools -> Command Palette...
    (Ctrl+Shift+P)`**
1. Type **`Preferences:
    Package Control Settings – User`** on the opened quick panel and press <kbd>Enter</kbd>
1. Then,
    find the following setting on your **`Package Control.sublime-settings`** file:
    ```js
    "channels":
    [
        "https://packagecontrol.io/channel_v3.json",
        "https://raw.githubusercontent.com/evandrocoan/StudioChannel/master/channel.json",
    ],
    ```
1. And,
    change it to the following, i.e.,
    put the **`https://raw.githubusercontent...`** line as first:
    ```js
    "channels":
    [
        "https://raw.githubusercontent.com/evandrocoan/StudioChannel/master/channel.json",
        "https://packagecontrol.io/channel_v3.json",
    ],
    ```
    * The **`https://raw.githubusercontent...`** line must to be added before the **`https://packagecontrol.io...`** one, otherwise,
      you will not install this forked version of the package,
      but the original available on the Package Control default channel **`https://packagecontrol.io...`**
    > [!WARNING]
    > Placing this custom channel before the default channel changes Package Control's resolution globally. Packages from this channel with the same name will override versions from the default channel.
    >
    > You can review the channel contents here:
    > https://raw.githubusercontent.com/evandrocoan/StudioChannel/master/channel.json
1. Now,
    go to the menu **`Preferences -> Package Control`**
1. Type **`Install Package`** on the opened quick panel and press <kbd>Enter</kbd>
1. Then,
    search for **`HighlightBuildErrors`** and press <kbd>Enter</kbd>

See also:

1. [ITE - Integrated Toolset Environment](https://github.com/evandrocoan/ITE)
1. [Package control docs](https://packagecontrol.io/docs/usage) for details.


# Configuration

As many Sublime Text plugins, the configuration can be modified from the menu `Preferences / Package Settings / Hightlight Build Errors`.

Here is the content of the default settings file:

```javascript
{
  // the plugin tests each regex and stops at the first match
  // "scope" is a key in the .tmTheme file
  // "display" can be "fill", "outline", "solid_underline", "stippled_underline" or "squiggly_underline"
  "colors": [
   {
      "regex": "note",
      "icon": "Packages/Highlight Build Errors/information.png"
    },
    {
      "regex": "warning",
      "scope": "invalid",
      "display": "outline",
      "icon": "Packages/Highlight Build Errors/warning.png"
    },
    {
      // default color, when none of the above matches
      "scope": "invalid",
      "display": "fill",
      "icon": "Packages/Highlight Build Errors/error.png"
    }
  ]
}

```


You can specify a regex on your project settings like this
```js
{
  "build_systems":
  [
    {
      // ...
    }
  ],
  "folders":
  [
    {
      "path": "."
    },
  ],
  "settings":
  {
    "tab_size": 2,
    "highlight_build_errors_result_file_regex": "^(..[^:]*):([0-9]+):?([0-9]+)?:? (.*)$"
  }
}
```

The `highlight_build_errors_result_file_regex` will be used for your project, instead of the standard `file_regex`.

The `highlight_build_errors_result_file_regex` an alternate error file regex for you build system,
other than the standard `file_regex` as when it is capturing more things which are not errors.


## Usage

Build as usual (<kbd>Ctrl</kbd>+<kbd>B</kbd> or <kbd>Cmd</kbd>+<kbd>B</kbd>).

Erroneous words or lines will be highlighted in the source files.

## Contributors

* Matthew Twomey
* Marcin Tolysz
* Connor Clark
* [Michael Yoo](https://github.com/sekjun9878) <michael@yoo.id.au>
* Aurelien Grenotton
* @evandrocoan

## Credits

* [Icons from famfamfam.com](http://www.famfamfam.com/lab/icons/silk/)


## License

See the `LICENSE` file under this repository.

