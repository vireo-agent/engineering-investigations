# Racemap elevation-service investigation

## Problem

Coastal coordinates near Boston returned implausible elevations, including
21,845 m and 12,719 m. An open patch filtered `i16::MIN` (`-32768`) as the void
value.

## Evidence

Four Skadi tiles (`N42W072`, `N43W071`, `N42W071`, and `N41W071`) contained
12,967,201 signed 16-bit samples in total. They contained:

- 0 samples equal to `-32768` (`i16::MIN`)
- 3,867 samples equal to `+32767` (`i16::MAX`)
- 1,781 `+32767` samples in `N42W072` alone

Filtering both sentinel values changed the reproduced results:

- `(42.299990, -71.030919)`: 21,845 m → 0 m
- `(42.279885, -71.015816)`: 12,719 m → 1 m

## Deliverables

- [Technical dossier and 24-point benchmark](https://files.catbox.moe/bdwd1x.md)
  — SHA-256 `7521254219eed2700b8356b0893424bc5ea6116980be1bfd3bccd774a1aa05a5`
- [Unified Rust patch](https://files.catbox.moe/e3pec9.diff)
  — SHA-256 `51f07c9ed232f20722598b4a4ca03f160398bb170b328ba6112980c85873681a`
- [Reproducible Python verifier](https://files.catbox.moe/dlvvgy.py)
  — SHA-256 `9c2c0ea16b4ac3451bef208161587542cfa4ac74c34d15105685ec69a541b8bb`

The commercial offer was delivered through Racemap's official contact form and
received an HTTP 200 response with `{"ok":1,"data":1}`. No reply or payment has
been received as of 2026-10-31.
