# Wisp

**Real-time messaging where conversations disappear.**

Wisp is a secure communication platform built around presence and ephemerality. Watch messages appear character-by-character as they're typed, then let them fade away. No history, no pressure — just authentic connection.

---

## What Makes Wisp Different

### Live Typing
See every keystroke in real time. No more "typing..." indicators — you're watching the conversation unfold as it happens.

### Ephemeral by Design
Messages disappear 5–30 seconds after they're seen. Nothing is saved, nothing is stored. When the conversation ends, it's gone.

### Presence-Bound Chat
You can only talk when you're both there. When someone leaves, the session dissolves. This creates genuine presence — like being in the same room.

### Peer-to-Peer Architecture
Messages travel directly between devices using WebRTC. Your conversations never touch a central server*, giving you genuine privacy without trusting a middleman.

<sub>*Socket.IO is used for signaling and presence only. Message content routes through encrypted P2P connections.</sub>

---

## Technical Overview

| Layer | Technology |
|-------|------------|
| iOS Client | Swift, SwiftUI |
| Real-time Transport | WebRTC Data Channels |
| NAT Traversal | Twilio STUN/TURN |
| Signaling & Presence | Socket.IO |
| Fallback Relay | Socket.IO (last resort) |

### Connection Flow

```
┌─────────────────────────────────────────────────────┐
│               CONNECTION PRIORITY                    │
├─────────────────────────────────────────────────────┤
│  1. WebRTC Direct (P2P)  → Lowest latency           │
│  2. WebRTC via TURN      → Still E2E encrypted      │
│  3. Socket.IO Relay      → Fallback only            │
└─────────────────────────────────────────────────────┘
```

The app automatically negotiates the best available connection. Users see a status indicator showing whether they're on a direct P2P connection, relayed through TURN, or using the server fallback.

---

## Philosophy

Most messaging apps are built around permanence — archiving every conversation, building searchable histories, creating a record of everything you've ever said.

Wisp takes the opposite approach. We believe some conversations are better when they're allowed to breathe and then disappear. Real-time typing creates intimacy. Ephemerality removes pressure. Presence makes every moment matter.

---

## Status

Wisp is currently in active development. The iOS app is available via TestFlight.

---

## Contact

Built by [@kierancrown](https://github.com/kierancrown)
