# ContentFarm

A local video studio that runs on one gaming GPU. It writes scripts, renders visuals, voices them and cuts them into finished short videos, and it can edit a recording you already have by editing its transcript. Everything runs on my own machine, with no paid video or voice APIs.

**Source:** private, available on request


## Why I built it

I wanted to make video for my own projects without paying per clip for every AI video, voice and editing service. I had one RTX 3090, so the question was how much of that pipeline one consumer GPU could run if the software was smart about it.

## What it does

- **Edit by transcript.** Open a recording, get a numbered transcript, and cut ums, long pauses and retakes by editing the text. It can also apply a recipe on its own (clean up, make a short, a podcast clip, a tutorial) and export to DaVinci Resolve, Premiere or Shotcut.
- **Make a video from a prompt.** One request turns into a script, visuals, a voiceover and a cut, rendered for each platform's size.
- **Motion graphics** from templates, rendered locally.
- **Review its own output.** A local vision model watches the finished video and flags problems before I post anything.
- **Drive it from an AI agent.** The whole studio is exposed as tools an agent like Claude can call, so I can ask for a video in plain English.

## The hard part

One 24 GB GPU can hold the writing model or the rendering model, not both. So the studio has to schedule its own GPU: swap models in and out between jobs, never kill a model that's busy, and keep long jobs moving when another job needs the card. Getting that reliable is what lets a single gaming PC do the work of several paid services.

## Built with

TypeScript on Node (API server and job runner), SQLite, React for the web app, a Tauri desktop shell, Python for the voice and music servers, llama.cpp for the language model and ComfyUI for rendering, all on one RTX 3090.

## Status

A working tool I use for my own projects. The source is private. If you're reviewing my work for a role, ask me and I'll walk you through it.
