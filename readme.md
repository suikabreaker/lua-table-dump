# lua table dump

A function to dump a lua table in proper format.

## Installation

It has no dependence, but require LuaJIT to run.

```bash
luarocks install https://raw.githubusercontent.com/suikabreaker/table_dump/master/table_dump-1.0-1.rockspec
```

## Usage

Example:

```lua
local table_dump = require 'table_dump'
local test = {
    key = "value",
    dict = {
        nested_key = '1',
        1, 2, 3
    }
}

print(table_dump(test, -1, true))
```

API:
```
function table_dump(value: any, indent: any, try_tostring: any)  -> string
```

`value` accept almost all kind of Lua values. `indent` defaults to `2`, and you can use `-1` to output in single line without any indent. When `try_tostring` set to true, the function will try `tostring` to output the table before DFS into it.