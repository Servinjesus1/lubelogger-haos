# lubelogger-haos
Unofficial Home Assistant OS app package for LubeLogger v1.7.5.

## Install

[Open LubeLogger in the Home Assistant app store](https://my.home-assistant.io/redirect/supervisor_addon/?addon=lubelogger&repository_url=https%3A%2F%2Fgithub.com%2FServinjesus1%2Flubelogger-haos)

To add the repository manually, use:

`https://github.com/Servinjesus1/lubelogger-haos`

## Status

This package is experimental. The patch has applied cleanly to Lubelogger `v1.7.5`, published successfully with .NET 10, and an ingress-style runtime test returned HTTP `200`.

The app now enables both Home Assistant ingress and direct port access:

- Direct port: `http://homeassistant.local:8080`
- Ingress: open LubeLogger from the Home Assistant sidebar or **Settings > Apps**

Ingress uses `X-Ingress-Path` and ASP.NET `PathBase`, with a `<base>` element and JavaScript AJAX URL prefix.

## Thanks and references

This project is derived from and thanks [pewingfield/haos-apps](https://github.com/pewingfield/haos-apps), whose Lubelogger app folder provided the original packaging approach.

Lubelogger itself is developed by [hargata/lubelog](https://github.com/hargata/lubelog).

- [Original pewingfield HAOS Lubelogger app](https://github.com/pewingfield/haos-apps/tree/main/lubelogger)
- [LubeLogger upstream repository](https://github.com/hargata/lubelog)
- [LubeLogger website](https://lubelogger.com)

Lubelogger and Hargata Softworks are not affiliated with this repository.

## To-Do

- [x] Enable HAOS ingress and direct Web UI access in `config.yaml`.
- [ ] Replace or dynamically rewrite remaining hardcoded absolute routes in `v1.7.5`.
- [ ] Verify remaining Razor `<a>`, `<img>`, `<form>`, and JavaScript navigation URLs under Home Assistant ingress.
- [ ] Replace server-generated root-relative redirect and download paths if browser-side prefixing is insufficient.
- [ ] Verify SignalR, file uploads/downloads, backups, restore, login, registration, logout, and redirects in an actual HAOS Ingress session.
- [ ] Test direct port `8080` behavior separately from ingress.
- [ ] Build the complete HAOS add-on Docker image on `amd64`.
- [ ] Validate upgrade and downgrade persistence in `/data`.
- [ ] Re-enable authentication and verify that ASP.NET Data Protection keys survive restarts.
- [ ] Update `config.yaml` and `haos.patch` together for future Lubelogger releases.
