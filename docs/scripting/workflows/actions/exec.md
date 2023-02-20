# `Exec`

The `Exec` action executes a specified binary and passes the arguments to it.

The workflow will wait until the program has exited before it continues.

## Inputs

 * `file` - a string pointing to the binary to execute.
 * `args` - a string array with arguments to pass to the executable.

## Example usage

```lua
local Workflow = require "porla.Workflow"
local Exec     = require "porla.actions.Exec"

return Workflow:new{
  on      = "TorrentAdded",
  actions = {
    Exec:new{
      file = "/usr/bin/curl",
      args = {
        "https://www.google.com"
      }
    }
  }
}
```