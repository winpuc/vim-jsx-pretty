vim-jsx-pretty
=======

The React syntax highlighting and indenting plugin for vim. Also supports the typescript tsx file.

Features
---

- Support JSX highlighting and indenting out of the box. No dependencies.
- Fully implemented the JSX syntax specification. [https://github.com/facebook/jsx](https://github.com/facebook/jsx)
- Support React syntax highlighting and indenting for JSX and typescript TSX files.
- Support JSX syntax highlighting and indenting inside the [tagged template](https://github.com/developit/htm) string.
- Support highlighting the close tag separately from the open tag (`let g:vim_jsx_pretty_highlight_close_tag = 1`).
- Many more [corner test cases](test.js) covered.
- [Reasonable syntax highlight groups](#syntax-group-list), easy for customization.

Demo
---

- syntax

|vim-jsx-pretty<br />(add colorful config)|vim-jsx-pretty|mxw/vim-jsx|
|---|---|---|
|![vim-jsx-pretty colorful](https://raw.githubusercontent.com/MaxMEllon/demos/master/vim-jsx-pretty/vim-jsx-pretty-colorful.png)|![vim-jsx-pretty](https://raw.githubusercontent.com/MaxMEllon/demos/master/vim-jsx-pretty/vim-jsx-pretty.png)|![vim-jsx](https://raw.githubusercontent.com/MaxMEllon/demos/master/vim-jsx-pretty/vim-jsx.png)|

- auto indent

![Auto indent demo](https://raw.githubusercontent.com/MaxMEllon/demos/master/vim-jsx-pretty/auto-indent.gif)

- support typescript

![typescript demo](https://user-images.githubusercontent.com/9594376/32855974-beb2432a-ca86-11e7-99a4-85c2630aa5d5.png)

Optional Dependencies
---

- [**pangloss/vim-javascript**](https://github.com/pangloss/vim-javascript)

or

- [othree/yajs.vim](https://github.com/othree/yajs.vim)

Installation
---

### vim-plug [https://github.com/junegunn/vim-plug](https://github.com/junegunn/vim-plug)

your `~/.vimrc`:

- No dependencies

    ```vim
    Plug 'maxmellon/vim-jsx-pretty'
    ```

- with: vim-javascript (**Recommendation**)

    ```vim
    " pangloss/vim-javascript is optional
    Plug 'pangloss/vim-javascript'
    Plug 'maxmellon/vim-jsx-pretty'
    ```

- if you want to highlight tsx files.

    ```vim
    Plug 'leafgarland/typescript-vim'
    Plug 'maxmellon/vim-jsx-pretty'
    ```

- with: yajs.vim

    ```vim
    " othree/yajs.vim is optional
    Plug 'othree/yajs.vim'
    Plug 'maxmellon/vim-jsx-pretty'
    ```

- Execute command in vim:

    ```vim
    :so ~/.vimrc
    :PlugInstall
    ```

### Syntax group list

|name|place|
|---|---|
|jsxElement| `<tag id="sample">text</tag>`<br />`~~~~~~~~~~~~~~~~~~~~~~~~~~~`|
|jsxTag| `<tag id="sample">`<br />`~~~~~~~~~~~~~~~~~`|
|jsxTagName| `<tag id="sample">`<br />`_~~~_____________`|
|jsxComponentName| `<Capitals>`<br />`_~~~~~~~~_` |
|jsxAttrib| `<tag id="sample">`<br />`_____~~__________`|
|jsxEqual| `<tag id="sample">`<br />`_______~_________`|
|jsxString| `<tag id="sample">`<br />`________~~~~~~~~_`|
|jsxCloseTag| `</tag>`<br />`~~~~~~` |
|jsxCloseString| `<tag />`<br />`_____~~` |
|jsxDot| `<Parent.Child>`<br />`_______~______` |
|jsxNamespace| `<foo:bar>`<br />`____~____` |
|jsxPunct| `<tag></tag>`<br />`~___~~~___~` |


Configuration
---

|name|default|description|
|---|---|---|
|`g:vim_jsx_pretty_template_tags`|`['html', 'raw']`|highlight JSX inside the tagged template string, set it to `[]` to disable this feature|
|`g:vim_jsx_pretty_colorful_config`|0|colorful config flag|

Colorful style (**vim-javascript only**)

```vim
let g:vim_jsx_pretty_colorful_config = 1 " default 0
```

Inspiration
---

- [vim-jsx](https://github.com/mxw/vim-jsx)

LICENSE
---
[MIT](./LICENSE.txt)
