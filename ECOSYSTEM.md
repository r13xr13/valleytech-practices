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

---

## 9. New Entities Discovered

### 9.1 Black Wire Militia

Black Wire Militia is a **team within the Watch Dogs Go Wars (WDGWars) wardriving game**, not an independent hacking group. The game is a Polish-based ARG (Alternate Reality Game) that turns WiFi/BLE wardriving into a competitive team sport.

| Detail | Value |
|--------|-------|
| Platform | wdgwars.pl — Watch Dogs Go Wars |
| Team size | 138/200 members (as of May 2026) |
| Other teams | Digital Ghost Collective (170/200), Watch Dogs OG's (68/200), Biscuits (56/200), CHAOS (7/200), and 25+ others |
| Game type | Wardriving ARG — collect WiFi and BLE network data, upload to platform, compete for badges and team ranking |
| Integration | Has its own Bruce firmware fork (LOCOSP/bruce-firmware-wdgwars) and Hak5 WiFi Pineapple Pager payload (LOCOSP/pineapple_pager_wdgwars) |
| YouTuber | GhostStrats covered it: "Watch Dogs Go Wars Just Turned Wardriving Into a Real Game!" |

The connection to this investigation: **WDGWars uses Bruce firmware** as its primary data collection tool. This means the Bruce firmware ecosystem directly feeds this competitive wardriving platform.

### 9.2 wdgwars.pl / Watch Dogs Go Wars

| Detail | Value |
|--------|-------|
| Website | wdgwars.pl |
| Press kit | wdgwars.pl/press |
| Developer | LOCOSP (also filed Bruce firmware Issue #1702 about GPS) |
| Created | ~April 2026 |
| Purpose | Gamified wardriving competition — "Watch Dogs Go Wars" |
| Bruce fork | github.com/LOCOSP/bruce-firmware-wdgwars (v1.0-wdgwars, 14 stars, 3 forks) |
| Pineapple integration | github.com/LOCOSP/pineapple_pager_wdgwars — Hak5 WiFi Pineapple Pager payload |
| API | POST /api/upload-csv endpoint, rate limited to 30/min |
| Badges | Hak5 Pager Op badge, team ranking, per-session statistics |
| Upload format | WigleWifi-1.6 CSV |

LOCOSP (the developer) is also a Bruce firmware user who filed issue #1702 about GPS functionality — showing this is a community member who built on top of Bruce, not an exploiter.

### 9.3 Talking Saquatch (skizzophrenic)

**DIRECT CONNECTION TO HALEHOUND AND VALLETECH CONFIRMED**

TalkingSaquatch (GitHub: skizzophrenic, YouTube: @TalkingSasquach) is a Flipper Zero content creator who has been directly integrated into the HaleHound development circle.

**Evidence of Connection:**

1. **HaleHound-CYD v3.5.5 release credits** (the official GitHub release):
   ```
   @valleytechsolutions, @TalkingSasquach, @Notorious-Squirrel,
   @Man-In-The-Mayhem, @Hamspiced — For the efforts and ideas that
   created the OPSEC of the HaleHound
   ```
   Talking Saquatch is credited **alongside ValleyTech** as a co-contributor to HaleHound's OPSEC features.

2. **ValleyTech's "Cinder Ferret V1" video** (May 21, 2026) directly shouts out:
   - `@TalkingSasquach`
   - `@GhostStrats`
   - `@Hedge-Tech-95`
   - Ham Spice from Midwest Gadgets
   - Jesse Hail (JesseCHale)

3. **ValleyTech says in the video**: "I love these developers with all my heart because this is what happens when awesome devs work together for a common cause"

**Talking Saquatch's Primary Identity:**

| Detail | Value |
|--------|-------|
| GitHub | skizzophrenic (1,882 followers) |
| YouTube | @TalkingSasquach — Flipper Zero tutorials |
| Website | talkingsasquach.com |
| Primary content | Flipper Zero animations, SquachWare CFW, Evil Portal, WiFi board binaries |
| Key repos | Talking-Sasquach (731★), Ubers-SD-Files (1,334★), SquachWare-CFW (358★) |
| Normal role | Flipper Zero community educator and CFW developer |
| Connection | Integrated into HaleHound inner circle alongside ValleyTech |

Talking Saquatch is primarily a Flipper Zero content creator who was brought into the HaleHound development orbit. Their involvement with OPSEC features for HaleHound is notable because their audience is primarily Flipper Zero users — meaning HaleHound is being cross-promoted into the Flipper community through this connection.

### 9.4 GhostStrats (YouTuber)

GhostStrats covered both:
- WDGWars wardriving game
- Connected to ValleyTech's ecosystem (shouted out in Cinder Ferret video)

This creates a triangle: **ValleyTech → GhostStrats → WDGWars** — with all three connected through the same YouTube/content creator ecosystem.

### 9.5 Midwest Gadgets (Ham Spice)

Referenced by ValleyTech as the hardware partner who co-designed the Cinder Ferret board for HaleHound:
> "Ham Spice from Midwest Gadgets and Jesse Hail have teamed up to produce something pretty cool"

This makes Midwest Gadgets a hardware fabrication partner for HaleHound — they're manufacturing the companion boards for ESP32-DIV-derived HaleHound firmware.

---

## 10. Updated Network Map

```
                  ┌──────────────────────────────────┐
                  │       JesseCHale (JMFH)          │
                  │       HaleHound-CYD              │
                  │       Proprietary firmware        │
                  └──────────┬───────────┬───────────┘
                             │           │
              ┌──────────────┘           └──────────────┐
              ▼                                         ▼
   ┌──────────────────────┐              ┌─────────────────────┐
   │  ValleyTech           │              │  Midwest Gadgets    │
   │  (Khalil Alarqawi)    │              │  (Ham Spice)        │
   │  Springfield, VA      │              │  Hardware mfr       │
   │  96K YouTube          │              │  Cinder Ferret board│
   │  Promotes HaleHound   │              └─────────────────────┘
   │  Sells RF Reaper      │
   │  Shills "dual core"   │
   └───────┬───────────────┘
           │                                ┌─────────────────────┐
           ├────────────────────────────────┤  Talking Saquatch   │
           │                                │  (skizzophrenic)    │
           │                                │  Flipper Zero YouTuber
           │                                │  Credited in Hale- │
           │                                │  Hound v3.5.5      │
           │                                │  OPSEC collaborator │
           │                                └─────────────────────┘
           │
           ├────────────────────────────────┐
           │                                ▼
           │                     ┌─────────────────────┐
           │                     │  GhostStrats         │
           │                     │  YouTuber            │
           │                     │  Covers WDGWars      │
           │                     │  Connected to VT     │
           │                     └─────────────────────┘
           │
           ▼
   ┌──────────────────────┐
   │  WDGWars.pl           │
   │  Watch Dogs Go Wars   │
   │  Polish wardriving ARG│
   │  Uses Bruce firmware  │
   │  Teams:               │
   │   Black Wire Militia  │
   │   Digital Ghost Coll. │
   │   Watch Dogs OG's     │
   │   +25 others          │
   └──────────────────────┘
```

---

## 11. Cross-Promotion Pipeline

The network functions as a cross-promotion machine across multiple communities:

```
HaleHound-CYD (JesseCHale)
  ↘ Promoted by ValleyTech (96K subs) — brings YouTube audience
    ↘ Promoted by Talking Saquatch (Flipper audience) — brings Flipper community
      ↘ Promoted by GhostStrats — brings wardriving/gaming audience
        ↘ Hardware made by Midwest Gadgets (Ham Spice)
          ↘ Sold through ValleyTech's Shopify
            ↘ Data uploaded to WDGWars for gamification
              ↘ Participation through Bruce firmware forks
```

Everyone in this network benefits from each other's audiences and platforms. The "open-source community" rhetoric masks what is essentially a closed commercial ecosystem where:
- CiferTech (ESP32-DIV original creator) gets nothing
- justcallmekoko (ESP32 Marauder) gets nothing
- pr3y (Bruce firmware) gets recognition but no hardware revenue
- The people **selling** and **cross-promoting** capture all the value

---

## 12. What Clean Looks Like (Comparison)

Compare this network with how healthy open-source projects operate:

| Aspect | HaleHound Network | GhostESP Ecosystem |
|--------|------------------|-------------------|
| Attribution | Missing/attacked | Credits all upstream |
| License | Proprietary (was MIT) | GPL-3.0 |
| Source | Closed | Open |
| Hardware partners | ValleyTech (cross-promotion) | Rabbit Labs, Wired Hatters (transparent) |
| Money flow | All to resellers | Partial to hardware makers, credit to devs |
| Community response to criticism | Hidden insults, block critics | Open issues, public discussion |

---

## 13. Person Directory (Updated)

| Person | Role | Status in Network |
|--------|------|-------------------|
| **Khalil Alarqawi/Yasin** | Owner, ValleyTech Custom Solutions | **Core orchestator / commercial node** |
| **JesseCHale (JMFH)** | Creator, HaleHound-CYD | **Core developer** |
| **Talking Saquatch (skizzophrenic)** | Flipper Zero YouTuber, OPSEC collaborator | **Cross-promotion partner** |
| **Ham Spice (Midwest Gadgets)** | Hardware designer, Cinder Ferret | **Hardware partner** |
| **GhostStrats** | YouTuber, covers WDGWars | **Cross-promotion partner** |
| **LOCOSP** | Developer, WDGWars platform | **Adjacent (Bruce ecosystem)** |
| **Cifer (cifertech)** | Creator, ESP32-DIV | **Victim (no credit)** |
| **Illya (Arch Labs)** | 15-year-old independent seller | **Victim (lost $2,080)** |
| **pr3y** | Creator, Bruce firmware | **Adjacent (source of Bruce forks)** |
| **Smoochiee** | Designer, RF Reaper PCB | **Adjacent (design exploited by VT)** |
| **r13xr13** | Investigator | **Blackballed from community** |
