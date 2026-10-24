# Hjortebjærg Server Panel

A small, private web control panel for our family's self-hosted **Minecraft Bedrock Dedicated Server**.
It runs on a mini PC at home and is only reachable on our home network. Four players (parents and kids)
play together on PS4, PS5, iPad and PC.

The code is private; this page describes the project.

## What it does

- Starts, stops and backs up our worlds (each world is a Docker container with its own LAN address, so
  consoles see all of them under *LAN Games*)
- Game rules, in-game messages, play-time stats and a map of each world
- Manages the **add-on library**: which add-ons each world uses, which version it runs, and updating
  them safely (backup first, then restart, only when nobody is playing)

## How it uses the CurseForge API

Bedrock add-ons are the one part that is hard to keep track of by hand: where did this pack come from,
who made it, and is there a newer version? The panel uses the CurseForge API to:

1. **Search** Bedrock add-ons and show their name, author, summary and CurseForge page
2. **Install** the author's file into our server's add-on library (only for our own server)
3. **Check once a night** whether the ~12 add-ons we use have a newer file

What it doesn't do:

- No re-hosting or sharing of files. Downloads go straight to our own server, for our own family.
- Authors who disallow third-party downloads are respected. The panel only links to the CurseForge page,
  and we download it there ourselves.
- No public website, no user accounts, no ads, no monetisation.

Expected traffic is tiny: a few searches now and then, plus one update check per night.

## Contact

Questions about this project: open an issue on this repository.
