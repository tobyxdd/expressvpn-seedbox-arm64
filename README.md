# ExpressVPN Seedbox Setup for ARM64 SBCs

- Uses official ExpressVPN Linux client (with Lightway support)
- Aria2 with AriaNg web frontend
- Tested on Khadas VIM4 (Ubuntu 22.04)

## Notes

- You MUST change `CHANGE_THIS` entries in `docker-compose.yml` before use
- Make sure `ARIA2RPCPORT` is the same as the port you expose on your host

## TODO

- Add SMB server