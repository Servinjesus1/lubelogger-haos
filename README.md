# lubelogger-haos
Unofficial Home Assistant OS app package for LubeLogger v1.7.5

## Install

[Open LubeLogger in the Home Assistant app store](https://my.home-assistant.io/redirect/supervisor_addon/?addon=lubelogger&repository_url=https%3A%2F%2Fgithub.com%2FServinjesus1%2Flubelogger-haos)

To add the repository manually, use:

`https://github.com/Servinjesus1/lubelogger-haos`

## Status

This package is experimental. The source patch has applied cleanly, Lubelogger `v1.7.5` has published successfully with .NET 10, and an ingress-style runtime test returned HTTP `200`.

## To-Do

- [ ] Replace or dynamically rewrite remaining hardcoded absolute routes in `v1.7.5`.
- [ ] Prefix all `window.location.href`, Razor `<a>`, `<img>`, `<form>`, and `fetch` URLs with `X-Ingress-Path` / `PathBase`.
- [ ] Replace the `window.location.href = data` patterns that return server-generated root-relative paths.
- [ ] Verify SignalR, file uploads/downloads, backups, restore, login, registration, logout, and redirects in an actual HAOS Ingress session.
- [ ] Test direct port `8080` behavior separately from ingress.
- [ ] Build the complete HAOS add-on Docker image on `amd64`.
- [ ] Validate upgrade and downgrade persistence in `/data`.
- [ ] Re-enable authentication and verify that ASP.NET Data Protection keys survive restarts.
- [ ] Update `config.yaml` and `haos.patch` together for future Lubelogger releases.
