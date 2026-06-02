# TODO

- [*] Verify the order in which dependencies are installed
- [*] Update the local repository if outdated
- [ ] Handle naming conflicts (install folder, package names, DCU folder names)
- [ ] Delphi environment variable BLOCKSDIR
- [ ] Import and export of the dependency database so the same environment can be recreated on another machine
- [ ] Support for platforms other than Win32 and Win64
- [ ] New repository location (private repo? HTTP url? Authentication?)
- [ ] New manifest scripts, such as a `copy`, `cmd`, `rename`, ... (see [Scripts](#scripts))
- [ ] `build` or `compile` command that recompiles an already installed package
- [ ] GUI version
- [ ] Expert version to be installed in the IDE

## Scripts

Example configuration:

```json
{
  "description": "Copy README.md",
  "command": "copy",
  "event": "afterCompile",
  "args": "*.README %DCU_PATH%"
}
```

* `command`: required
* `description`: optional, shown during the install process
* `event`: required
* `args`: optional (but may be required for some commands)

Available commands:

* `copyres`: copies resources and dfm files *(already implemented)*
* `copy source target`: copies the given files (supports wildcards)
* `move source target`: moves the given files (supports wildcards)
* `echo [arg1 [arg2 [...]]]`: prints the arguments *(already implemented)*
* `cmd [arg1 [arg2 [...]]]`: runs the given commands
* `bat filename`: runs the given batch file
