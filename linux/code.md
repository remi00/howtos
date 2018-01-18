## Visual Studio Code

Install Code and Fira Mono:
```sh
yaourt -S visual-studio-code-bin otf-fira-mono
```

### Characters issues in terminal

If the characters are broken in the integrated terminal, just add to settings:

```json
{
  "terminal.integrated.setLocaleVariables": true
}
```

### Settings

```json
{
    "window.zoomLevel": 1,
    "terminal.integrated.shell.linux": "/usr/bin/zsh",
    "editor.fontFamily": "Fira Code",
    "editor.fontLigatures": true,
    "editor.fontSize": 13,
    "terminal.integrated.fontFamily": "'Fira Mono for Powerline'",
    "terminal.integrated.fontSize": 12,
    "terminal.integrated.setLocaleVariables": true,
    "terminal.integrated.lineHeight": 1,
    "editor.tabSize": 2,
    "editor.cursorBlinking": "phase",
    "files.trimTrailingWhitespace": true,
    "files.insertFinalNewline": true,
    "workbench.iconTheme": "material-icon-theme",
    "[javascript]": {
        "editor.tabSize": 2,
        "editor.insertSpaces": true
    },
    "[vue]": {
        "editor.tabSize": 2,
        "editor.insertSpaces": true
    },
    "eslint.options": {
        "extensions": [".html", ".js", ".vue", ".jsx"]
    },
    "eslint.validate": [
        {
            "language": "html",
            "autoFix": true
        },
        {
            "language": "vue",
            "autoFix": true
        },
        {
            "language": "javascript",
            "autoFix": true
        },
        {
            "language": "javascriptreact",
            "autoFix": true
        }
    ]
}
```
