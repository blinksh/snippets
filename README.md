# Snips
This is a WIP. For an introduction, please visit the [documentation](https://docs.blink.sh/basics/snips).

This is the default Index that is automatically updated by Blink within the app. Its purpose is to provide basic and common UNIX functionality. We have mainly referred to https://www.stationx.net/unix-commands-cheat-sheet/ while creating this Index, but we welcome your assistance in improving the guidelines and adding new commands to this Index through PRs.

Before release, we plan to add the functionality to include other Index locations, which will allow for additional community-maintained Indexes such as Linux commands or even specific development tools (I need one for Rust :D). We found creating this Index to be incredibly helpful and we hope that others can benefit and learn from it as well.

## Guidelines

Nothing here is written in stone. So please let us know if something does not make sense or it could be improved.

### Naming
- Incorporate recognizable command names into the action name. For example, for a command like `head` we named a snip `read-from-head` to convey its command and purpose more clearly.
- For commands that are already recognizable verbs, consider organizing them into separate folders. For example, use `ssh` instead of `remote-connection` or `grep` instead of `search/strings`. By doing so, you can focus the snips within the folder on specific action names. For example, within the "ssh" folder, you can have Snippets like `ssh/connect` while in the "grep" folder, you can have Snippets like `grep/string`. This enhances clarity and makes it easier to discover.
- Focus on describing the action, specially with abbreviated commands. For instance, instead of `netstat-ports` we use a more descriptive `net/list-ports-status` to accurately reflect the Snip's purpose.
- To make it easier to discover relevant snips, consider dividing actions with multiple flags. When getting more specific, incorporate additional details into the names. For instance, we have `tar/extract` and `tar/extract-element`.
- Use descriptive verbs when naming actions. Opt for terms like "list" or "read" instead of generic terms like "display" or "show." This consistency makes it easier to surface snips with fuzzy search, for example, `net/ls` will show `net/list-interface`, `net/list-ports`, etc…

### Template tags
- The same template tag can be used multiple times and it will be replaced everywhere at once.
- For commands that may accept multiple sequential parameters, use sequential names. For example `${file_1}` `${file_2}`.
- Use tag names that feel like a continuation of the whole action. For example, in `files/symbolic-link` we use `${path}` `${to_link_name}`
- If a parameter can be optional, try to embed in the tag. For example `ssh/connect` uses `${user@}``${host_hash_port}`
- A parameter may have multiple options. You can embed them all in the tag, and (upcoming) comments will context on what they do. For instance, `permissions/set` uses `${ago}` for **a**ll, **g**roup, **o**thers.
