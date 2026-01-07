# Runtime Tickrate Changer

Allows changing the tickrate of the server at runtime.
Thanks to [ficool2](https://github.com/ficool2) for discovering this method.

> [!NOTE]
> As of now, this only supports **Team Fortress 2** on **32-Bit Linux**.
>
> Anyone is free to contribute gamedata and functionality for other games and platforms, but I probably won't do it myself.

## Requirements

* [SourceMod 1.12+](https://www.sourcemod.net)

## Usage

The plugin defines a console command `sm_tickrate` and a console variable `sm_interval_per_tick`. The convar default is set to the game's default tick interval.

You need to call or set either of these **before** level change for it to have any effect.
It is safe to do so at any time during or before the `OnMapEnd` forward, as the new tickrate will only be applied on level change.

Calling `sm_tickrate` with a value of `0` will return the server to the default tickrate. Alternatively, `sm_interval_per_tick` can also be reset to its default value using `sm_resetcvar`.

If you need the tickrate to be applied on server start or persist throughout the server's lifetime, the `-tickrate` launch parameter can be used.
