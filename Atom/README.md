# [default-config](../README.md)
### Configurações do Atom

init script

```coffee
atom.commands.add 'atom-text-editor',
  'custom:insert-seta': ->
    atom.workspace.getActiveTextEditor()?.insertText('->')

  'custom:insert-seta-array': ->
    atom.workspace.getActiveTextEditor()?.insertText('=>')

  'custom:insert-dump-die': ->
    atom.workspace.getActiveTextEditor()?.insertText('dump();die();')

  'custom:insert-var_dump-die': ->
    atom.workspace.getActiveTextEditor()?.insertText('var_dump();die();')

  'custom:insert-console-log': ->
    atom.workspace.getActiveTextEditor()?.insertText('console.log()')

# atom.getCurrentWindow().on 'blur', ->
#   for pane in atom.workspace.getPanes()
#     pane.saveItems()

atom.getCurrentWindow().on 'blur', ->
  for pane in atom.workspace.getPanes()
    for item in pane.items
      if item.isModified and item.getPath()
        item.save()
```

keymap

```coffee
'atom-workspace atom-text-editor':
  'ctrl-.': 'custom:insert-seta'
  'ctrl->': 'custom:insert-seta-array'
  'ctrl-e': 'custom:insert-dump-die'
  'ctrl-alt-e': 'custom:insert-console-log'
  'ctrl-shift-e': 'custom:insert-var_dump-die'
  'ctrl-shift-up': 'editor:move-line-up'
  'ctrl-shift-down': 'editor:move-line-down'

'.windows .platform-linux':
  'ctrl-shift-r': 'tree-view:reveal-active-file'
```

snnipets

```coffee
'.source.php':
  'DumpAndDie':
    'prefix': 'dump'
    'body': 'dump($1);\ndie();'
  'QueryBuilder':
    'prefix': 'queryBuilder'
    'body': "$qb = $em->getRepository(${1:'AppBundle:Entity'})\n    ->createQueryBuilder('e')\n    ->getQuery()\n    ->getResult()\n;"
  'entityManager':
    'prefix': 'entityManager'
    'body': "$em = $this->getDoctrine()->getManager();\n"
```

config.json

```coffee
"*":
  "autocomplete-plus": {}
  core:
    allowPendingPaneItems: false
    audioBeep: false
    excludeVcsIgnoredPaths: false
    ignoredNames: [
      ".git"
      ".hg"
      ".svn"
      ".DS_Store"
      "._*"
      "Thumbs.db"
      "desktop.ini"
      "vendor"
    ]
    telemetryConsent: "no"
    themes: [
      "atom-dark-ui"
      "one-dark-syntax"
    ]
  editor:
    fontSize: 13
    invisibles:
      eol: " "
    showInvisibles: true
    softWrap: true
    tabLength: 4
  "exception-reporting":
    userId: ""
  welcome:
    showOnStartup: false
  whitespace:
    ensureSingleTrailingNewline: false
    ignoreWhitespaceOnCurrentLine: false
```
