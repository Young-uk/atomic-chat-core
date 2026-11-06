---
date: 2026-11-06
title: "Store one-time chat speech outside the audio gallery"
---

# 2026-11-06 — Store one-time chat speech outside the audio gallery

- **Context.** Chat playback used the gallery job path and removed clips after reading them. The gallery could list them while a chat was speaking.
- **Decision.** The audio job request can opt into transient output. The runner stores the WAV and its recipe in the separate chat-speech folder and retains the flag in the job and its events. The client reads the WAV and uses the existing delete call to discard it.
- **Consequences.** The normal gallery and its output setting continue to serve saved jobs. Transient output is excluded from gallery listings. An interrupted client may leave files in the separate folder.
- **Owner.** Team.
