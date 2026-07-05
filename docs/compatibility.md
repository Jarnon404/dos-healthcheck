# Compatibility notes

## Conservative baseline

`HEALTH.BAT` avoids modern command extensions and uses basic DOS batch syntax:

- `ECHO`
- `IF EXIST`
- `TYPE`
- `DIR`
- `VER`
- `PATH`
- `CHKDSK`
- output redirection with `>` and `>>`

This keeps the script suitable for MS-DOS 3.x, 4.x, 5.x and 6.x style systems.

## Date and time

`DATE /T` and `TIME /T` are intentionally not used in the baseline script because they are not a safe assumption for older DOS versions.

## DOS 6.x extensions

`HEALTH6.BAT` adds more detailed memory reporting with `MEM /C` and `MEM /D`, and checks for common DOS 6.x tools such as `MEMMAKER.EXE`, `SCANDISK.EXE` and `DEFRAG.EXE`.
