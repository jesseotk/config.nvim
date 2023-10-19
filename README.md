# Neovim config

### Installation

Requirements:
* Make sure to review the readmes of the plugins if you are experiencing errors. In particular:
  * [ripgrep](https://github.com/BurntSushi/ripgrep#installation) is required for multiple [telescope](https://github.com/nvim-telescope/telescope.nvim#suggested-dependencies) pickers.
* See [Windows Installation](#Windows-Installation) if you have trouble with `telescope-fzf-native`

Neovim's configurations are located under the following paths, depending on your OS:

| OS | PATH |
| :- | :--- |
| Linux | `$XDG_CONFIG_HOME/nvim`, `~/.config/nvim` |
| MacOS | `$XDG_CONFIG_HOME/nvim`, '~/.config/nvim` |
| Windows | `%userprofile%\AppData\Local\nvim\` |

Clone kickstart.nvim:

```sh
# on Linux and Mac
git clone https://github.com/ogjojo/config.nvim.git "${XDG_CONFIG_HOME:-$HOME/.config}"/nvim && mkdir "${XDG_CONFIG_HOME:-$HOME/.config}"/nvim/undodir
# on Windows
git clone https://github.com/ogjojo/config.nvim.git %userprofile%\AppData\Local\nvim\ 
```

### Re-installation

First clean up the old installation:

```sh
rm -rf ~/.local/share/nvim/lazy

# Optional if you want to create a backup of your old config
mv ~/.config/nvim ~/.config/nvim.old

rm -rf ~/.config/nvim
```

Then follow the installation steps above!

### Post Installation

Run the following command and then **you are ready to go**!

```sh
nvim --headless "+Lazy! sync" +qa
```

### Windows Installation

Installation may require installing build tools, and updating the run command for `telescope-fzf-native`

See `telescope-fzf-native` documentation for [more details](https://github.com/nvim-telescope/telescope-fzf-native.nvim#installation)

This requires:

- Install CMake, and the Microsoft C++ Build Tools on Windows

```lua
{'nvim-telescope/telescope-fzf-native.nvim', build = 'cmake -S. -Bbuild -DCMAKE_BUILD_TYPE=Release && cmake --build build --config Release && cmake --install build --prefix build' }
```

