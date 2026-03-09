# Networking – OSI Model Lesson Game

An interactive browser-based quiz game for teaching and reviewing the OSI model. Built for vocational networking and CIT students but works for anyone learning the OSI stack.

No server required. Single HTML file. Open it and go.

## What It Covers

- All 7 OSI layers — functions, devices, PDUs, addressing
- TCP vs UDP
- Layer-specific devices (hubs, switches, routers, proxies)
- Protocol Data Units (bits → frames → packets → segments → data)
- Common mnemonics (*All People Seem To Need Data Processing*)
- MAC sublayer vs LLC sublayer

## Question Types

**Multiple Choice** — standard question with 4 options, progressive hints if you're stuck, explanation after each answer

**Drag to Order** — arrange items in correct OSI sequence (layers, PDUs, devices)

**Matching** — pair items across two columns

## Structure

Two practice sets:

- **Practice 1** — Core layer identification, devices, addressing (10 questions)
- **Practice 2** — Transport protocols, PDUs, devices by layer, ordering (10 questions)

Each set ends with a score summary and option to retry.

## Hints System

Every question has three progressive hints — each one gets more specific. Use them before guessing rather than after. That's the point.

## How to Use

### Standalone
1. Download `index.html`
2. Open in any browser
3. Done

### On a School Server
Drop it anywhere on a web server. Students browse to it on their phones or computers during class or review. Works on mobile without modification.

### As a Template
The question data is a JSON object inside the HTML. Swap it out for any topic — TCP/IP, subnetting, routing protocols, whatever your curriculum needs. The game engine handles the rest.

## Customizing Questions

Find the `qdata` object in the script section. Each question follows this structure:

```json
{
  "id": "P1-1",
  "type": "mc",
  "prompt_html": "Routers primarily operate at which OSI layer?",
  "choices": ["Layer 2", "Layer 3", "Layer 4", "Layer 7"],
  "correct": "Layer 3 — Network",
  "hints": [
    "Think about logical addressing (IP).",
    "Devices that forward by IP live at this layer.",
    "Routers examine IP headers to choose paths — that's Layer 3."
  ],
  "explain": "Routing and logical addressing are Layer 3 functions."
}
```

For ordering questions use `"type": "order"` and `"orderTargets": [...]` with items in correct sequence.

## License

MIT — use it, modify it, share it. If you build a version for a different networking topic, consider sharing it back.

## Origin

Built for a vocational CIT classroom in Pennsylvania as supplemental practice before NOCTI assessments. Designed to run on student phones during review sessions without requiring a login, server, or network access beyond the initial page load.
