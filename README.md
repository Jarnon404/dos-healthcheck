# DOS Healthcheck

Retro-style system audit and health check toolkit for MS-DOS era machines.

This project is intentionally simple: plain batch files, classic DOS commands and text-based reports. The goal is to document the kind of system state that mattered in the DOS era: DOS version, conventional memory, CONFIG.SYS, AUTOEXEC.BAT, PATH, disk status and loaded tools or drivers.

## Compatibility target

| DOS version | Support level | Notes |
|---|---:|---|
| MS-DOS 3.x | Baseline | Uses conservative commands and syntax |
| MS-DOS 4.x | Baseline | Same baseline script |
| MS-DOS 5.x | Baseline plus better memory tooling | MEM is more useful |
| MS-DOS 6.x | Baseline plus extended script | `HEALTH6.BAT` can use more detailed memory checks |

## Scripts

```text
scripts/HEALTH.BAT   Baseline audit for DOS 3.x, 4.x, 5.x and 6.x
scripts/HEALTH6.BAT  Extended checks for DOS 6.x
```

## What it checks

- DOS version
- current directory and PATH
- root directory listing
- `C:\CONFIG.SYS`
- `C:\AUTOEXEC.BAT`
- memory status using `MEM` when available
- disk status using `CHKDSK`
- common DOS files such as `HIMEM.SYS`, `EMM386.EXE`, `SMARTDRV.EXE`, `MSCDEX.EXE`, `EDIT.COM` and `QBASIC.EXE`

## Output

```text
DOS-REPORT.TXT
DOS6-REPORT.TXT
```

## Why?

Because many IT careers started long before dashboards, agents and cloud portals. Sometimes the original monitoring stack was `MEM`, `DIR`, `TYPE`, `CHKDSK` and a human staring at a beige screen.

## Safety model

The scripts are read-only. They collect command output into text reports and do not change `CONFIG.SYS`, `AUTOEXEC.BAT` or system files.

## Public safety note

This repository is intended to contain only public-safe material. Do not commit customer-specific data, tenant identifiers, credentials, generated audit reports, internal hostnames, private IP addresses or environment-specific exports.
