# Vim and Neovim Tips and Tricks

This document compiles various tips and tricks for enhancing your experience with Vim and Neovim, including configuration adjustments, keyboard shortcuts, and useful commands.

## Configuration Adjustments

- **Disable Indent Guides**: Use `:IndentGuidesEnable` followed by `:nohl #turn off highlights`.
- **Convert Spaces**: Use the command `:4,34s;^\(\s\+\);\=repeat(' ', len(submatch(0))/2);g` to convert 4 spaces to 2.
- **Pylint Integration**: Prefer `coc-pyright` over `coc-python` for a more sensitive integration with Pylint, such as underlining problematic words in the line.

## Keyboard Shortcuts

- **End of Line**: `$`
- **Start of Line**: `0`
- **Go to Next Line**: Return (Enter Key)
- **EOF**: `G`
- **Start of File**: `gg`
- **Move to Beginning of Next Word**: `w`
- **Move to Beginning of Previous Word**: `b`
- **Move to End of Next Word**: `e`
- **Move to End of Previous Word**: `ge`

## Selection in Vim

- **Select Inside Parentheses**: `Vib`
- **Select Inside Curly Blocks**: `viB`
- **Select Inside Parentheses Inclusively**: `vab`

## Deletion in Vim

- **Delete a Word Forward**: `dw`
- **Delete a Word Backward**: `db`
- **Delete a Line Forward**: `d$`
- **Delete All Lines Forward**: `dG`

## Clipboard Management

- **Copy to System Clipboard**: `"*y` or `"*d`
- **Delete in Visual Mode Without Cutting**: `"_d`
- **Delete Word When Cursor Is Inside**: `diw`

## Tab Management

- **Open New Tab**: `:tabnew (DIR)`
- **Next Tab**: `gt`
- **Prior Tab**: `gT`
- **Numbered Tab**: `(nnn) gt`

## Miscellaneous Commands

- **Front Deletion**: `fn + Del`
- **Go to Line Number**: `(line number) + G`
- **Redo**: `ctrl-r`
- **Comment From Cursor**: `<leader>cc`
- **Uncomment Multiple Lines**: `<leader>cu`
- **Comment Line Regardless of Cursor Location**: `<leader>cs`

## Disabling Floating Documentation in CoC

To disable the floating documentation of functions in CoC, add `"signature.enable": false` to your `coc-settings.json`. This setting can be found at https://github.com/neoclide/coc.nvim/issues/2233.

## Shell Command Insertion

- **Insert Shell Command Result**: `:exp1 :%!ls`
- **Use `%` for Current File Name**: `:exp2 :r echo %`

## Usage of Backslash in Linux Commands

The backslash `\` makes the next character act as a standalone character, without any special meaning used in a particular environment. Example: `:r date "+\%d"`.

## Internal Variables in Vim

Learn about internal variables in Vim using `:h`.

## Additional Tips

- **Soft Wrapping**: Use `:set wrap linewrap` for normal line wrapping behavior.
- **Switch Between Buffers**: `ctrl+^`
- **Spell Check**: `:set spell`
- **Ignore Case Sensitivity**: `:set ignorecase`
- **Center Cursor**: `zz`
- **Set Option Locally**: `:setlocal`
- **Change Selected Text Case**: Selected text + `u` (U) for uppercase/lowercase.
- **Join Lines**: `:[1,n]j`
- **Remove Duplicate Lines**: `:sort u`
- **Efficient Exit**: Use `:x` instead of `:wq`
- **Delete Rest of Line**: `D`
- **Neovim Diff Mode**: Configure with `git config merge.tool nvimdiff`
- **Search Through Files**: `:Ag` (with fzf)
- **Find Words Count**: `g + ctrl-g`
- **Close Buffer**: `:bd`

## TODO

- Learn and read about internal variables in Vim (`:h`).
- Explore `wemux` for remote collaborations in Vim/Neovim.
- Run a specific command immediately entering Vim: `nvim -c "THE_COMMAND"`
- Read more about Neovim's diff mode used in Git Mergetool to resolve merge conflicts.
- Find out the default config file path of Neovim: `:echo stdpath('config')`
