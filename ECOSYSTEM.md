# ESP32 Security Firmware Ecosystem: Lineage, Attribution & Commercial Pipelines

**Author:** r13xr13
**Date:** May 2026

---

## Why This Document Exists

HaleHound-CYD and ValleyTech are not isolated actors. They are nodes in a larger ecosystem where open-source community work gets extracted, rebranded, and sold — often with the original creators receiving neither credit nor compensation.

This document maps the full ecosystem to show who built what, who credits whom, who profits, and who gets left behind.

---

## 1. Firmware Lineage Map

```
ESP32 Marauder (justcallmekoko, 2020, MIT)
  First ESP32 security firmware. Created the template.
  │
  ├── Conceptual inspiration (NOT code copy)
  │    └── ESP32-DIV (cifertech, 2024, MIT)
  │         First to integrate WiFi + BLE + SubGHz + NRF24 + RFID.
  │         3,000+ GitHub stars. Original work.
  │         │
  │         ├── GIT FORK (history severed) ──────────────────────────────┐
  │         │    JesseCHale/ESP32-DIV ("HaleHound Edition", Jan 2026)   │
  │         │    Orphan root commit f8a659c. 17,253 lines re-committed. │
  │         │    Cifer's 19 commits erased.                             │
  │         │    │                                                      │
  │         │    └── CONCEPTUAL PORT (not git fork)                     │
  │         │         JesseCHale/HaleHound-CYD (Feb 2026)               │
  │         │         94% icons bit-identical. 90%+ submenu code copy.  │
  │         │         Source closed Apr 2026.                           │
  │         │         Hidden Base64: "FUCK YOU CIFER"                  │
  │         │         └── RockBase-iot fork preserves original history  │
  │         │
  │         └── Conceptual inspiration (unattributed)
  │              └── Bruce firmware (pr3y, 2025, AGPL-3.0)
  │                   Independent codebase. Missing Marauder/ESP32-DIV
  │                   credit in acknowledgements.
  │                   └── Hardware: RF Reaper (designed by Smoochiee)
  │                        CERN-OHL-P-2.0 open hardware license
  │                        Made by Elecrow, sponsored by PCBWay
  │                        RESELLERS:
  │                         - BruceDevices (official Elecrow store, $80)
  │                         - ValleyTech (unofficial, $80, exploited Illya)
  │                         - Hack-Box (reseller)
  │
  └── Conceptual inspiration + credited
       └── GhostESP (Spooks4576 → GhostESP-Revival, GPL-3.0)
            Detached fork of archived Spooks4576/Ghost_ESP.
            Maintained by jaylikesbunda (Jay Candel).
            ESP-IDF native + LVGL UI — completely independent.
            Best attribution practices in the ecosystem.
            Credits: Marauder, Spacehuhn, Flipper Zero,
                     DarkFlippers, xMasterX, Spooks4576.
            Hardware Partners:
             - Rabbit Labs (Ghost Board, Phantom, Poltergeist, Minion)
             - Wired Hatters (The Banshee, Ultimate Marauder, Pocket Ghost)
```

## 2. Attribution Report Card

| Project | Credits Upstream? | License | Source Public? | Verdict |
|---------|------------------|---------|----------------|---------|
| **ESP32 Marauder** | N/A (original) | MIT | Yes | Clean |
| **ESP32-DIV** | Missing Marauder credit | MIT | Yes | Minor gap |
| **HaleHound-CYD** | **Severed. Buried. Attacked.** | **Proprietary** | **No** | **Systematic fraud** |
| **Bruce firmware** | Missing Marauder/ESP32-DIV | AGPL-3.0 | Yes | Attribution gap |
| **GhostESP** | Credits all known sources | GPL-3.0 | Yes | Gold standard |

### What Good Attribution Looks Like (GhostESP README)

GhostESP explicitly credits:
- JustCallMeKoKo — "ESP32Marauder foundational development"
- SpacehuhnTech — "Reference deauthentication code"
- Spooks4576 — "Original GhostESP Developer"
- Flipper Zero firmware — "Core IR & NFC implementation"
- DarkFlippers — "SubGHz protocol decoders"
- xMasterX — "SubGHz improvements"

This is how it should be done.

### What Bad Attribution Looks Like (HaleHound)

- Source header says: `// Based on ESP32-DIV HaleHound Edition by Jesse (JesseCHale)` — credits **his own fork**, not CiferTech's original
- README says: `*I built this.*` — sole authorship claim
- No CiferTech credit anywhere in the README
- Issues asking for credit (#47, #50, #52, #59) closed without resolution
- Hidden Base64 insult attacking Cifer and baobuiquang

---

## 3. Commercial Entities Map

```
                    OPEN SOURCE FIRMWARE
    ┌─────────────────┬────────┬──────────┬──────────────┐
    │  ESP32 Marauder │ESP32-DIV│  Bruce  │   GhostESP   │
    │      (MIT)      │  (MIT)  │ (AGPL)  │    (GPL)     │
    └────────┬────────┴────┬───┴────┬─────┴──────┬───────┘
             │             │        │            │
    ┌────────▼─────────┐   │        │            │
    │ justcallmekoko   │   │        │            │
    │ LLC (sells HW)   │   │        │            │
    └──────────────────┘   │        │            │
                           │        │            │
             ┌─────────────▼──┐  ┌──▼────────────┴────────┐
             │  BruceDevices  │  │  GhostESP Hardware      │
             │  (Elecrow store)│  │  Partners                │
             │  RF Reaper $80 │  │  Rabbit Labs             │
             │  Bruce PCB V2  │  │  Wired Hatters           │
             └────────┬───────┘  └─────────────────────────┘
                      │
         ┌────────────┼────────────┐
         ▼            ▼            ▼
  ┌───────────┐ ┌──────────┐ ┌──────────┐
  │ValleyTech │ │ Hack-Box │ │Arch Labs │
  │ (Khalil)  │ │ (resell) │ │ (Illya)  │
  │ $80/unit  │ │          │ │ VICTIM   │
  │ Shopify + │ │          │ │ Lost     │
  │ Elecrow   │ │          │ │ $2,080   │
  └───────────┘ └──────────┘ └──────────┘

            MANUFACTURERS
    ┌─────────────────┬──────────────┐
    │     Elecrow     │    PCBWay    │
    │ PCB + assembly  │ PCB + sponsor│
    │ Marketplace     │              │
    │ 5% commission   │              │
    └─────────────────┴──────────────┘
```

## 4. The Profit Pipeline

### Pipeline A: ESP32-DIV → HaleHound → Closed-Source Fame

```
CiferTech creates ESP32-DIV (MIT, free)
  → JesseCHale forks, severs history, re-commits 17,253 lines
    → Rebrands as HaleHound-CYD, adds skull theme
      → Closes source, distributes binaries only
        → YouTube videos, GitHub stars, reputation
          → CiferTech gets nothing. No credit. No compensation.
            → When asked for credit: "FUCK YOU CIFER"
```

### Pipeline B: Bruce Firmware → RF Reaper → Resale

```
pr3y builds Bruce firmware (AGPL, free)
  → Smoochiee designs RF Reaper PCB (CERN-OHL-P-2.0)
    → Elecrow and PCBWay manufacture
      → BruceDevices sells officially ($80)
        → ValleyTech resells ($80)
          → Illya (Arch Labs) buys 10 units at $65 each
            → Boards arrive incomplete (bare PCBs)
              → Elecrow offers $75 refund on $1,055 order
                → Illya spends $1,100 more to finish boards
                  → ValleyTech announces $80 version
                    → Illya cannot compete. Loses $2,080.
                      → ValleyTech keeps selling.
```

### Pipeline C: GhostESP → Hardware Partners

```
GhostESP (GPL-3.0, free)
  → Rabbit Labs sells Ghost Board pre-flashed
    → Wired Hatters sells The Banshee pre-flashed
      → GhostESP developers credited in product pages
        → Community model working as intended
          → (Rare case where attribution is done right)
```

---

## 5. The ValleyTech Network

ValleyTech Custom Solutions (Khalil Alarqawi/Yasin, Springfield VA) sits at the center of multiple revenue streams built on open-source community work:

| Revenue Stream | Source | Price | Attribution to Original Creators? |
|---------------|--------|-------|-----------------------------------|
| RF Reaper (resold) | Smoochiee/BruceDevices | ~$80 | No (product page mentions Bruce, not Smoochiee) |
| M5Stack accessories | Open hardware community | $6-$9 | Unclear |
| Flipper Zero Pwnagotchi board | Open hardware community | $18.99 | Unclear |
| Flipper Zero RGB mod | Mail-in service | $65 | N/A (service) |
| CC1101 Radio Module | Standard component | $7.99 | N/A (standard part) |
| Digimon F-com PCB | Open hardware community | $7.99 | Unclear |
| YouTube channel | Technology content | Ad revenue | N/A |
| BuyMeACoffee | Community tips | Tips | N/A |

Total products on Shopify: ~20. YouTube subs: ~96K. Videos: ~850. Total views: ~6M. Elecrow store: 3 products.

---

## 6. The People

| Person | Role | Location |
|--------|------|----------|
| **Khalil Alarqawi (Khalil Yasin)** | Owner, ValleyTech Custom Solutions | Springfield, VA 22150 |
| **JesseCHale (JMFH)** | Creator, HaleHound-CYD | Unknown (online only) |
| **Cifer (cifertech)** | Creator, ESP32-DIV | Unknown (online only) |
| **pr3y** | Creator, Bruce firmware | Unknown (online only) |
| **Smoochiee** | Designer, RF Reaper PCB | Brazil |
| **Pirata (bmorcelli)** | Core developer, Bruce + Marauder | Unknown |
| **jaylikesbunda (Jay Candel)** | Maintainer, GhostESP: Revival | Philippines (Stefanini IT) |
| **Spooks4576** | Original creator, GhostESP | Unknown (archived project) |
| **Illya** | Victim, Arch Labs (15 years old) | Unknown |
| **r13xr13** | Investigator, repo author | Unknown |

---

## 7. The Pattern

When you look across this ecosystem, a pattern emerges:

### The Attribution Fraud Pattern (HaleHound)
1. Find successful open-source MIT project
2. Fork, sever git history
3. Re-commit all code under new name
4. Port to new hardware (legitimate effort)
5. Rebrand, distance from original
6. Claim sole authorship
7. Close source
8. Attack critics

### The Commercial Exploitation Pattern (ValleyTech)
1. Build platform (YouTube, Shopify, Elecrow)
2. Use community language ("educational", "bigger brother")
3. Acquire design files through private channels
4. Shift financial risk to others (Illya pays, ValleyTech profits)
5. Undercut anyone who tries to compete
6. Control the narrative through platform advantage
7. Silence dissenters

### The Healthy Pattern (GhostESP)
1. Build on open-source foundations
2. Credit everyone explicitly in README
3. Keep full source public
4. Use standard open-source license (GPL-3.0)
5. Partner with hardware vendors transparently
6. Welcome community contributions

---

## 8. What You Can Do

If you are building ESP32 security firmware or hardware:

- **If you fork or port:** Keep the original author's name in the README, in the source headers, and on the splash screen. Write a credits section. Do not claim "I built this" if someone else built the foundation.
- **If you sell hardware:** Credit the firmware developers and hardware designers. Pay them if you profit. At minimum, link to their work.
- **If you see attribution fraud:** Document it with public evidence. File issues. Speak up. The community can only police itself.
- **If you see exploitation:** Call it out. Support the victim. Do not let the narrative controller silence the truth.

The Hacker Manifesto says: *"This is our world now... the world of the electron and the switch, the beauty of the baud."* That world belongs to everyone who builds in it, not just the people who take and sell.

---

## Repository Links

- [r13xr13/halehound-analysis](https://github.com/r13xr13/halehound-analysis) — HaleHound forensic analysis
- [r13xr13/valleytech-practices](https://github.com/r13xr13/valleytech-practices) — ValleyTech investigation
- [cifertech/ESP32-DIV (original, MIT)](https://github.com/cifertech/ESP32-DIV)
- [JesseCHale/HaleHound-CYD](https://github.com/JesseCHale/HaleHound-CYD)
- [pr3y/Bruce (AGPL)](https://github.com/pr3y/Bruce)
- [BruceDevices/firmware](https://github.com/BruceDevices/firmware)
- [GhostESP-Revival/GhostESP (GPL)](https://github.com/GhostESP-Revival/GhostESP)
- [justcallmekoko/ESP32Marauder (MIT)](https://github.com/justcallmekoko/ESP32Marauder)
- [RockBase-iot/HaleHound-CYD (preserved history)](https://github.com/RockBase-iot/HaleHound-CYD)
