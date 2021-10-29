# rdx_status

- [RDX Framework Discord](https://discord.gg/VkhUUGHpNs)

## Download & Installation

- Download https://github.com/Redm-Extended-PT/rdx_status

  [INSTALLATION]

- Put it in the `[rdx]` directory
- Import `rdx_status.sql` in your database
- Add this in your `server.cfg`:

```
ensure rdx_status
```

[HOWTO]

server.lua
```lua

local name    = 'hunger'
local default = 1000000
local color   = '#CFAD0F'

TriggerEvent('rdx_status:registerStatus', name, default, color, 
	function(status) -- Visible calllback, if it return true the status will be visible
		return true
	end,
	function(status) -- Tick callback, what to do at each tick
		status.remove(200)
	end,
	{remove = 200} -- Client action (add / remove) so the client can be in sync with server
)


```
