# [default-config](../README.md)
### Configurações do Sublime

Preferences > key bindings
```json
[
    { "keys": ["ctrl+shift+b"], "command": "toggle_side_bar"},
    { "keys": ["alt+shift+up"], "command": "select_lines", "args": {"forward": false}},
    { "keys": ["alt+shift+down"], "command": "select_lines", "args": {"forward": true}},
    { "keys": ["ctrl+shift+r"], "command": "reveal_in_side_bar"},
    { "keys": ["ctrl+e"], "command": "insert", "args": {"characters": "dump();\ndie();"} },
    { "keys": ["ctrl+shift+e"], "command": "insert", "args": {"characters": "var_dump();\ndie();"} },
    { "keys": ["ctrl+["], "command": "insert", "args": {"characters": "$foo = $em->getRepository('BarBundle:Bar')\n    ->createQueryBuilder('foo')\n->getQuery()\n->getResult();"} },
    { "keys": ["ctrl+."], "command": "insert", "args": {"characters": "->"} },
    { "keys": ["ctrl+shift+."], "command": "insert", "args": {"characters": "=>"} },
    { "keys": ["ctrl+alt+e"], "command": "insert", "args": {"characters": "console.log()"} }
]
```

Preferences > settings
```json
{
    "always_show_minimap_viewport": true,
    "atomic_save": true,
    "default_line_ending": "unix",
    "draw_white_space": "all",
    "ensure_newline_at_eof_on_save": true,
    "font_size": 10,
    "highlight_line": true,
    "ignored_packages":
    [
        "Vintage"
    ],
    "rulers":
    [
        80,
        120
    ],
    "save_on_focus_lost": true,
    "tab_completion": false,
    "tab_size": 4,
    "translate_tabs_to_spaces": true,
    "trim_trailing_white_space_on_save": true,
    "word_separators": "./\\()\"'-:,.;<>~!@#%^&*|+=[]{}`~?",
    "word_wrap": "true"
}
```
