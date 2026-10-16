---
title: Apps
description: Known apps that run emulator cores, their canonical slugs, and the cores they run.
---

An app is the software or device that runs an [emulator core](/registries/cores/): a frontend that loads cores, an FPGA
device that loads them as bitstreams, or a standalone emulator built around an engine of its own. The Universal Saves
Format carries it in a [`source`](/specifications/bundle/#source-map)'s `app` field, beside the core in `core`, because
one app runs many cores and one core runs in many apps.

The slug is what a producer writes in `app` when a save was produced by that app. An app listed here MUST use its slug
rather than a reverse-DNS name, even if it holds a domain, so that one app has one spelling. A slug is the name the app
already goes by, lowercased, with every run of other characters replaced by a single `-`. The result conforms to the
[slug grammar](/specifications/common-types/slug/) every vocabulary here shares.

A firmware that ships an app is not an app here but a [platform](/registries/platforms/). muOS and most handheld
firmwares run RetroArch, so a save they wrote names `retroarch` as its `app` and the firmware as its `platform`. A
device whose firmware loads cores itself, such as the Analogue Pocket, has no app inside it to name, so the device is
the app and is listed here. A producer that runs no core, such as a cartridge reader or a service, has no entry here and
names itself in reverse-DNS.

The **Cores** column says what the app runs: a **Kind** from the [Emulator Cores registry](/registries/cores/) for an
app that loads every core of that kind, or core slugs for one that runs only its own.

The list is **non-normative** and first-come; to add an app, open a PR with a row, alphabetical by slug.

| Slug              | App             | Cores      |
| ----------------- | --------------- | ---------- |
| `analogue-pocket` | Analogue Pocket | `openfpga` |
| `mister`          | MiSTer          | `mister`   |
| `retroarch`       | RetroArch       | `libretro` |
