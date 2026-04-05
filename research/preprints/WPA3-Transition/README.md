# WPA3 Transition Mode — Empirical Security Audit

**Status:** In progress — pre-data collection  
**Target:** Mid-2026 draft, December 2026 submission  

---

## Overview

This paper empirically audits the security of WPA2/WPA3 mixed-mode (transition mode) deployments on consumer-grade hardware, focusing on whether WPA3's SAE authentication guarantees hold in practice when backward compatibility is enabled.

Motivated by Vanhoef & Ronen's Dragonblood (2019), which demonstrated protocol-level downgrade vulnerabilities in WPA3/SAE, this work asks a narrower but underexplored question: have consumer vendors correctly implemented the post-Dragonblood mitigations in shipping firmware, and does transition mode reliably preserve SAE's security guarantees for capable clients?

---

## Research Questions

- **RQ1** — Can a WPA2 4-way handshake or PMKID be captured from a WPA3-capable client connecting to a transition-mode AP?
- **RQ2** — Can active downgrade attacks (deauthentication, beacon manipulation) reliably force WPA2 negotiation in mixed-mode environments?
- **RQ3** — Does vulnerability to the above vary across consumer vendors and firmware versions?
- **RQ4** — What configurations, if any, meaningfully reduce consumer exposure?

---

## Scope

| In scope | Out of scope |
|---|---|
| Consumer-grade routers, 3–5 devices | Enterprise 802.1X / RADIUS |
| Named firmware versions, documented | SAE cryptographic analysis |
| Passive handshake / PMKID capture | Real-world network scanning |
| Active downgrade via deauth | Novel protocol-level attacks |
| Defensive recommendations | Claims beyond tested hardware |

---

## Key Prior Work

- Vanhoef & Ronen — *Dragonblood: Analysing WPA3's SAE Handshake* (2019)
- Vanhoef — *PMKID attack* (2018)
- IEEE 802.11-2020 standard
- Wi-Fi Alliance WPA3 Specification

---

## Ethical Statement

All testing is conducted on hardware owned and controlled by the researcher, using isolated test SSIDs with no connection to production networks or third-party devices. This work is framed within a responsible disclosure and defensive security context.

---

## Milestones

| Period | Goal |
|---|---|
| Now → June 2026 | Literature review, hardware acquisition, environment setup |
| June → August 2026 | Data collection — RQ1 and RQ2 |
| August → October 2026 | Cross-vendor analysis, RQ3/RQ4, first draft |
| October → December 2026 | Revision, formatting, submission |
