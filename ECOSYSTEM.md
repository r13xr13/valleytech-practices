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

---

## 14. Deep Dive: All Network Entities

### 14.1 Midwest Gadgets LLC (hamspiced / Nick)

**The Rosetta Stone of the network.** Midwest Gadgets is the hardware design node that connects nearly every entity in this ecosystem.

| Detail | Value |
|--------|-------|
| Owner | **Nick** (hamspiced / hamspice) |
| Website | midwestgadgets.org |
| Tindie store | tindie.com/stores/hamspiced/ |
| Founded | February 2024 |
| Original focus | Biohacking — RFID subdermal implant readers |
| Product lines | NFC repeaters, field visualizers, Kiisu devboards, Proxmark3 accessories, RFID extenders, **Cinder Ferret**, **Piglet** |
| GitHub | github.com/hamspiced (open source hardware) |
| Forums | DangerousThings forum (biohacking community) |

**Products:**

**Cinder Ferret** — Companion PCB for HaleHound CYD that integrates Ebyte E01 (NRF24) and Ebyte E07 (CC1101) modules. Described as "the official HaleHound add-on PCB." Designed by Ham Spice and Jesse Hail. Sold through halehound.com. ValleyTech promotes and resells these.

**Piglet** — ESP32 Xiao-C5 powered wardriver. Key details from the product page:
> *"The only other approved vendor for these is Kal over at ValleyTechSolutions.tech"*
> *"When it connects, enter in your WatchDogGoWars API Key and your Wigle Token"*
> Price: $75

**The Piglet Credits Section — The Network Exposed:**
> *"Special thanks to:*
> - *Bread @Breadboxsystems*
> - *Hedge@Biscuitshop.us (Hedge-Tech-95)*
> - *Kal@Valleytechsolutions.tech*
> - *Rabbit@Rabbitlabs.com*
> - *BillieGreen@TheWiredHatters.com*
> - *SpuriousIndices@YourMom"*

This single line documents the entire cross-entity network in one place.

**Relationship to the investigation:**
- Designed the Cinder Ferret (HaleHound hardware) → directly supports the proprietary firmware
- Credits ValleyTech as "only other approved vendor" → formal business partnership
- Integrates with WDGWars → connects HaleHound hardware to the wardriving game
- Credits Rabbit Labs + Wired Hatters → bridge to GhostESP ecosystem
- Credited in HaleHound releases as OPSEC collaborator → part of inner development circle

### 14.2 Rabbit Labs

| Detail | Value |
|--------|-------|
| Website | rabbit-labs.com |
| Role | GhostESP official hardware partner |
| Products | Ghost Board (ESP32-C6), Phantom (touch handheld), Poltergeist (ESP32-C5), Minion, Yapper Board |
| Relationship | GhostESP hardware partner — ships pre-flashed with GhostESP firmware |
| Connected to | Midwest Gadgets (Piglet credits), ValleyTech (cross-promotion) |
| Also sells | ZR Kraken cases (mentioned in ValleyTech Lab5 video) |

Rabbit Labs is one of the **GhostESP official hardware partners** (alongside Wired Hatters). Their presence in the Piglet credits confirms they're part of the same cross-promotion network, even though GhostESP itself is a clean GPL project.

### 14.3 Wired Hatters (BillieGreen)

| Detail | Value |
|--------|-------|
| Website | wiredhatters.com |
| Role | GhostESP official hardware partner |
| Former name | Flipper Hub (no longer used) |
| Products | The Banshee (€239.99, dual ESP32-C5 + S3), Ultimate Marauder, Pocket Ghost, ESP-Rocket |
| Location | Germany |
| Relationship | GhostESP hardware partner — credits "Deki" (jaylikesbunda) as main developer |
| Connected to | Midwest Gadgets (Piglet credits), Rabbit Labs, ValleyTech |

Wired Hatters' **The Banshee** has its own subdomain (banshee.ghostesp.net) and they explicitly credit Deki/GhostESP. This is transparent hardware partnership done right — the contrast with ValleyTech's exploitation is stark.

### 14.4 Hedge-Tech-95 / Hedge (Biscuitshop.us)

| Detail | Value |
|--------|-------|
| YouTube | @Hedge-Tech-95 |
| Business | Biscuitshop.us |
| Role | Hardware maker, cross-promotion partner |
| Mentioned by | ValleyTech in Cinder Ferret V1 video (shoutout) |
| Connected to | Midwest Gadgets (Piglet credits), ValleyTech |

ValleyTech shouted out @Hedge-Tech-95 in the Cinder Ferret video alongside Talking Saquatch and GhostStrats. Midwest Gadgets' Piglet credits "Hedge@Biscuitshop.us." This is another hardware/content creator in the cross-promotion network.

### 14.5 GhostStrats

| Detail | Value |
|--------|-------|
| GitHub | @Ghoststrats (34 followers, joined 2024) |
| YouTube | @GhostStrats |
| Website | ghoststrats-shop.fourthwall.com |
| Content | WDGWars coverage, WiFi Pineapple Pager, Biscuit Pro, cybersecurity gadgets |
| Connected to | ValleyTech (shouted out in Cinder Ferret video), WDGWars (made a video about it) |

GhostStrats is the YouTube bridge between the **wardriving game community (WDGWars)** and **ValleyTech's promotion network**. Their video "Watch Dogs Go Wars Just Turned Wardriving Into a Real Game" is how the ARG gained visibility.

### 14.6 LOCOSP (WDGWars Creator)

| Detail | Value |
|--------|-------|
| GitHub | LOCOSP |
| Project | WDGWars (wdgwars.pl) — Watch Dogs Go Wars ARG |
| Bruce fork | github.com/LOCOSP/bruce-firmware-wdgwars (14 stars) |
| Pineapple payload | github.com/LOCOSP/pineapple_pager_wdgwars |
| Bruce issue | Filed Issue #1702 about GPS on Bruce firmware |
| Role | Developer who built a wardriving game platform on top of open-source tools |

LOCOSP is a **Bruce firmware community member** who created a gaming layer on top of wardriving. They are not directly part of the ValleyTech network but their platform is used by it — the Piglet wardriver (Midwest Gadgets + ValleyTech) uploads data to WDGWars.

### 14.7 Talking Saquatch (skizzophrenic) — Deeper Profile

| Detail | Value |
|--------|-------|
| Real name | Unknown |
| GitHub | skizzophrenic (1,882 followers, joined 2016) |
| YouTube | @TalkingSasquach (Flipper Zero tutorials, 131K subscribers estimated) |
| Website | talkingsasquach.com (footer: "inspired by jbohack") |
| Key repos | Talking-Sasquach (731★), Ubers-SD-Files (1,334★), SquachWare-CFW (358★), awesome-flipperzero (108★), flipper-zero-evil-portal (74★) |
| CFW | SquachWare Custom Firmware for Flipper Zero |
| Normal content | Flipper Zero animation tutorials, Pwnagotchi builds, 3D printed cases |
| ESP32 content | Dual Boot ESP32 S3 bins, WiFi board binaries |
| Connected to | ValleyTech, JesseCHale (credited in 3 HaleHound releases), Midwest Gadgets (indirect) |

**How they're connected:**
- Credited in HaleHound-CYD v3.2.0, v3.5.0, and v3.5.5 release notes as an "OPSEC" collaborator
- Listed alongside ValleyTech in HaleHound credits: *"@duggie162-cpu, @ValleytechSolutions, @TalkingSasquach... — The efforts and ideas that created the OPSEC of the HaleHound"*
- Shouted out by ValleyTech in the Cinder Ferret video
- jbohack connection: JesseCHale contributed to jbohack/nyanBOX; Talking Saquatch's website credits jbohack — this creates a triangle

Talking Saquatch is primarily a **Flipper Zero content creator** who was recruited into the HaleHound inner circle to provide OPSEC feature concepts. Their involvement brings the **Flipper Zero community audience** into the HaleHound orbit — cross-promotion from Flipper to ESP32/CYD.

### 14.8 Other Credits in HaleHound Releases

| Person | Role | When Credited |
|--------|------|---------------|
| **duggie162-cpu** | RFID recommendation, Lunatic Fringe concept, EAPOL bug reports | v3.2.0 |
| **CircuitZ** | IoT Recon idea | v3.2.0 |
| **muffduncan** | Captive Portal update | v3.2.0 |
| **Notorious-Squirrel** | OPSEC collaborator | v3.2.0+ |
| **Man-In-The-Mayhem** | OPSEC collaborator | v3.2.0+ |
| **hamspiced** | OPSEC collaborator (Midwest Gadgets owner) | v3.2.0+ |

These individuals formed the development circle around HaleHound. Whether they were aware of the attribution fraud (CiferTech credit removal, license change, Base64 insult) is unknown — but they were part of the ecosystem that benefited from it.

---

## 15. The Complete Network Topology

```
                          CiferTech (ESP32-DIV, MIT)
                               │ (created the foundation)
                               ▼
                    JesseCHale (HaleHound-CYD)
                    Proprietary, source closed
                    "I built this." + "FUCK YOU CIFER"
                               │
          ┌────────────────────┼──────────────────────────┐
          ▼                    ▼                          ▼
 ┌──────────────┐   ┌──────────────────┐   ┌────────────────────────┐
 │   ValleyTech  │   │ Midwest Gadgets  │   │  Talking Saquatch       │
 │  (Khalil)     │   │ (hamspiced/Nick) │   │  (skizzophrenic)        │
 │  Springfield  │   │  Hardware design │   │  Flipper Zero YouTuber  │
 │  VA           │   │  Cinder Ferret   │   │  OPSEC collaborator     │
 │  96K YT subs  │   │  Piglet wardriver│   │  731★ GitHub            │
 │  Shopify      │   │  NFC/RFID tools  │   │  jbohack connected      │
 │  Elecrow      │   └────────┬─────────┘   └────────────────────────┘
 │  Promotes HH  │            │
 └──────┬───────┘             │
        │                     │
        │         ┌───────────┴──────────────────┐
        │         │  Piglet Credits (The Network) │
        │         │  "Special thanks to:"         │
        │         │  - Bread@Breadboxsystems      │
        ├─────────┤  - Hedge@Biscuitshop.us       │
        │         │  - Kal@Valleytechsolutions    │
        │         │  - Rabbit@Rabbitlabs.com      │
        │         │  - BillieGreen@WiredHatters   │
        │         └───────────────────────────────┘
        │                     │
        ▼                     ▼
 ┌──────────────┐   ┌──────────────────┐
 │  Hedge-Tech  │   │  GhostStrats      │
 │  Biscuitshop │   │  YouTuber         │
 │  Hardware    │   │  WDGWars coverage │
 └──────────────┘   └────────┬─────────┘
                             │
                             ▼
                    ┌──────────────────┐
                    │  WDGWars (LOCOSP) │
                    │  wdgwars.pl       │
                    │  Wardriving ARG   │
                    │  Bruce firmware   │
                    │  + Pineapple      │
                    │  + Piglet uploads │
                    └──────────────────┘
                             │
                    ┌────────┴────────┐
                    ▼                 ▼
          ┌──────────────┐   ┌──────────────┐
          │ Rabbit Labs  │   │Wired Hatters  │
          │ GhostESP HW  │   │GhostESP HW   │
          │ Ghost Board  │   │The Banshee   │
          │ Phantom      │   │Ult. Marauder │
          └──────────────┘   └──────────────┘
```

## 16. What This Means

**ValleyTech (Khalil) is not the orchestrator of a conspiracy. He is a commercial node in a cross-promotion network** where:

1. **Open-source code flows in one direction** — from CiferTech (ESP32-DIV) → JesseCHale (HaleHound) → hardware sales + YouTube revenue
2. **Hardware flows through a closed circle** — Midwest Gadgets designs it, ValleyTech sells it, Rabbit Labs and Wired Hatters provide adjacent products
3. **Audiences cross-pollinate** — Talking Saquatch brings Flipper users, GhostStrats brings gamers, ValleyTech brings ESP32 hobbyists
4. **The original creators get nothing** — CiferTech, justcallmekoko, pr3y
5. **The victims get silenced** — Illya (Arch Labs) lost $2,080, r13xr13 got blackballed

The Piglet credits page is not a smoking gun of conspiracy. It is a **membership list for a closed commercial ecosystem** that benefits from open-source code without reciprocating.

---

## 17. What Could Be Done

- **CiferTech** could file a DMCA takedown against HaleHound-CYD for removing MIT copyright notices
- **Elecrow** could investigate ValleyTech's partner seller status for abusive practices
- **The community** could fork ESP32-DIV with proper attribution and active development (houndBEE-CYD is a start)
- **Illya** could pursue small claims court against ValleyTech for the incomplete RF Reaper order
- **Buyers** could choose GhostESP hardware partners (Rabbit Labs, Wired Hatters) who give proper attribution, instead of ValleyTech

---

## 18. Deep Dive: duggie162-cpu (Duggie)

**Profile Verification:**
- GitHub: github.com/duggie162-cpu
- Account created: 2026-01-02
- Followers: 31 | Public repos: 8
- Bio: "Flipper _ Ghost _ Tinker _ Hardware"
- Location: Earth I think

**Key Repository Analysis:**
- **CYD-INFO** (fork of BruceDevices/firmware)
  - Description: "Predatory ESP32 Firmware" 
  - Language: C | License: AGPL-3.0
  - Stars: 8 | Forks: 0
  - This is notable as a self-aware critique of the firmware ecosystem from someone within the HaleHound circle

**HaleHound Connection:**
- Credited in HaleHound-CYD v3.2.0 release notes (March 12 2026):
  *"PN532 RFID/NFC — Five attack modes: [...] (Shoutout: @duggie162-cpu for the RFID recommendation)"*
- Duggie provided the RFID module suggestion that led to the PN532 RFID/NFC module implementation
- No code commits found in HaleHound-CYD history (only release credit)

**Network Position:** 
Hardware enthusiast specializing in RFID/GPS modules who contributed feature ideas to HaleHound. Part of the broader Flipper Zero/GhostESP/HaleHound hobbyist ecosystem but not directly monetizing the project.

---

## 19. Deep Dive: CircuitZ (SLZLabs / J. Crider)

**Identity Verification:**
- GitHub login: SLZLabs (github.com/SLZLabs)
- Display name: CircuitZ (shown in profile name field)
- Commit identity: CircuitZ <j.crider@live.com> (confirmed in commit bbfd782)
- Account created: 2015-03-17
- Followers: 3 | Public repos: 5
- Bio: "Hi! I'm CircuitZ"
- Company: SLZ Cloud Play Club
- Location: The Internets

**Repository Portfolio:**
- HaleHound-CYD (fork, 0★)
- HaleHound-CYD-3.2-ESP32E-40R (WIP MOST STUFF IS BROKEN, 14★) 
- HAStuff (Various Things I've Done with Home Assistant, 0★)
- PagerPwn (Development Work for "A pocket-sized network pager", 5★)
- PineappleProjects (Various Payloads I created for the Pineapple, 0★)

**HaleHound Connection:**
- **PR #13** (March 13 2026): "Addt'l Wifiscan Filter and Client Counts"
  - Author: CircuitZ <j.crider@live.com> (commit bbfd782)
  - Added ability to filter out hidden SSIDs and show client counts in WiFi scan
  - PR author: SLZLabs (login), CircuitZ (display name) 
- **Release Credit**: HaleHound-CYD v3.2.0 (March 12 2026):
  *"IoT Recon — Automated LAN attack suite. [...] (Shoutout: @CircuitZ for reminding me to add IoT)"*
- CircuitZ suggested the IoT Recon module feature

**Network Position:**
Long-term GitHub user (since 2015) with Home Assistant and Pineapple payload experience. Contributed code (PR #13) and feature ideas to HaleHound. Operates at the hobbyist contributor level rather than commercial reseller.

---

## 20. Deep Dive: muffduncan

**Profile Verification:**
- GitHub: github.com/muffduncan
- Account created: 2026-03-09 (coincidentally same day as HaleHound v3.2.0 release?)
- Followers: 0 | Public repos: 0 | Following: 0
- Bio: (empty)
- No public activity beyond account creation

**HaleHound Connection:**
- Credited in HaleHound-CYD v3.2.0 release notes:
  *"Captive Portal Upgrade — PSK capture templates + Core 0 deauth task for continuous client disruption while serving portal pages. (Shoutout: @MuffDuncan for bringing it to my attention)"*
- Suggested improvements to the captive portal feature

**Assessment:**
Account appears to be a blank shell or alternate account created specifically to interact with the HaleHound project. No verifiable public identity or activity beyond the single release credit. Likely a community member who made a feature suggestion but did not maintain ongoing involvement.

**Network Position:**
Minimal, unverified contributor who made one feature suggestion. Represents the lowest level of community engagement in the HaleHound ecosystem.

---

## 21. Deep Dive: houndBEE (lordbuffcloud/houndBEE) - DELETED REPO

**Verification Status:**
- GitHub account: lordbuffcloud (user CK42X, Ohio, 87 public repos, created 2016-08-18)
- Repository: **lordbuffcloud/houndBEE** — **NOW DELETED** (returns 404)
- Web search confirmation: Was indexed by search providers as recently as May 2026
- Current status: Repository no longer accessible via GitHub API or web interface

**Repository Content (per web search index):**
- Fork of JesseCHale/HaleHound-CYD v3.5.5
- Description: "ESP32-DIV HaleHound Edition for Cheap Yellow Display - Multi-protocol offensive security toolkit"
- Part of CK42X device line: nyanBEE, flipperBEE, houndBEE
- Provided CK42X-branded web flasher at **[ck42x.com/houndbee/flash]**
- Had landing page at **[ck42x.com/houndbee]**
- Included CK42X-side docs and hardware guides
- Firmware binaries pulled directly from JesseCHale's GitHub releases
- Explicitly stated: "houndBEE is a community rebrand of [JesseCHale/HaleHound-CYD] by Jesse C. Hale. All firmware logic, radio drivers, attack modules, UI, and board support are his work."

**Key Correction to Previous Assertion:**
Contrary to earlier documentation, houndBEE **did NOT credit CiferTech/ESP32-DIV**. Instead, it credited JesseCHale as the originator of all substantive work, thus perpetuating the same attribution omission found in HaleHound itself. The repo was a rebrand of HaleHound, not a return to the original ESP32-DIV.

**Network Position:**
CK42X (lordbuffcloud) attempted to create a branded distribution of HaleHound with a web flasher service, then deleted the repository. This represents a commercialization attempt that was abandoned or replaced by other CK42X projects.

---

## 22. Additional Context: lordbuffcloud/nyanCOMP

**Verified Active Repository:**
- GitHub: github.com/lordbuffcloud/nyanCOMP
- Description: "FCC-compliant fork of the nyanBOX firmware. SigKill removed."
- Language: C++ | License: MIT
- Stars: 2 | Forks: 0
- Created: 2026-04-09

**Connection to HaleHound Ecosystem:**
- nyanCOMP is a fork of jbohack/nyanBOX (Flipper Zero RFID/NFC tool)
- JesseCHale (HaleHound creator) has contributed to **jbohack/nyanBOX** in the past
- This creates a connection chain: JesseCHale ↔ nyanBOX ↔ lordbuffcloud/nyanCOMP
- Modification: Removed SigKill (RF jamming tool) for FCC compliance
- Provides web flasher at **[ck42x.com/nyanbox-flasher]**

**Significance:**
Shows lordbuffcloud (CK42X) operates in both the Flipper Zero (nyanBOX) and ESP32/CYD (HaleHound) ecosystems, acting as a cross-pollinator between these communities. The nyanCOMP repo remains active while houndBEE was deleted.

---

## 23. Updated Network Topology with Entity Findings

```
                            CiferTech (ESP32-DIV, MIT)
                                   │ (created foundation)
                                   ▼
                    JesseCHale (HaleHound-CYD)
                    Proprietary, source closed
                    "I built this." + "FUCK YOU CIFER"
                                   │
          ┌────────────────────┼──────────────────────────┐
          ▼                    ▼                          ▼
 ┌──────────────┐   ┌──────────────────┐   ┌────────────────────────┐
 │   ValleyTech  │   │ Midwest Gadgets  │   │  Talking Saquatch       │
 │  (Khalil)     │   │ (hamspiced/Nick) │   │  (skizzophrenic)        │
 │  Springfield  │   │  Hardware design │   │  Flipper Zero YouTuber  │
 │  VA           │   │  Cinder Ferret   │   │  OPSEC collaborator     │
 │  96K YT subs  │   │  Piglet wardriver│   │  731★ GitHub            │
 │  Shopify      │   │  NFC/RFID tools  │   │  jbohack connected      │
 │  Elecrow      │   └────────┬─────────┘   └────────────────────────┘
 │  Promotes HH  │            │
 └──────┬───────┘             │
        │                     │
        │         ┌───────────┴──────────────────┐
        │         │  Piglet Credits (The Network) │
        │         │  "Special thanks to:"         │
        │         │  - Bread@Breadboxsystems      │
        ├─────────┤  - Hedge@Biscuitshop.us       │
        │         │  - Kal@Valleytechsolutions    │
        │         │  - Rabbit@Rabbitlabs.com      │
        │         │  - BillieGreen@WiredHatters   │
        │         └───────────────────────────────┘
        │                     │
        ▼                     ▼
 ┌──────────────┐   ┌──────────────────┐
 │  Hedge-Tech  │   │  GhostStrats      │
 │  Biscuitshop │   │  YouTuber         │
 │  Hardware    │   │  WDGWars coverage │
 └──────────────┘   └────────┬─────────┘
                             │
                    ┌──────────────────┐
                    │  WDGWars (LOCOSP) │
                    │  wdgwars.pl       │
                    │  Wardriving ARG   │
                    │  Bruce firmware   │
                    │  + Pineapple      │
                    │  + Piglet uploads │
                    └──────────────────┘
                             │
                    ┌────────┴────────┐
                    ▼                 ▼
          ┌──────────────┐   ┌──────────────┐
          │ duggie162-cpu  │   │ CircuitZ     │
          │ (RFID/GPS)     │   │ (J. Crider)  │
          │ Hobbyist       │   │ Contributor  │
          │ Suggestion:    │   │ Suggestion:  │
          │   RFID module  │   │   IoT Recon  │
          └──────────────┘   └──────────────┘
                             │
                    ┌────────┴────────┐
                    ▼                 ▼
          ┌──────────────┐   ┌──────────────┐
          │ muffduncan     │   │ lordbuffcloud│
          │ (shell account)│   │  (CK42X)     │
          │ Suggestion:    │   │ nyanCOMP     │
          │ Captive Portal │   │ (FCC nyanBOX)│
          │                │   │ houndBEE     │
          │                │   │ (DELETED)    │
          └──────────────┘   └──────────────┘
```

## 24. Key Insights from Entity Investigation

1. **The Suggestion Economy**: duggie162-cpu, CircuitZ, and muffduncan represent a tier of contributors who provided feature ideas (RFID, IoT Recon, Captive Portal) but received no direct financial benefit. Their contributions were acknowledged in release notes but not translated into economic participation.

2. **Commercialization vs. Contribution**: ValleyTech, Midwest Gadgets (Ham Spice), and CK42X (lordbuffcloud) attempted to monetize the HaleHound ecosystem through hardware sales (Cinder Ferret, Piglet, web flashers) while the idea-contributors remained in the hobbyist sphere.

3. **Attribution Omission Persists**: Even fork/rebrand efforts like houndBEE failed to correct the core attribution problem—they credited JesseCHale instead of tracing back to CiferTech/ESP32-DIV, showing how the attribution error propagates through the ecosystem.

4. **Ephemeral Contributions**: Some contributions exist only as release credits (muffduncan) or deleted repositories (houndBEE), highlighting the transient nature of some community involvement.

5. **Cross-Pollination Hubs**: Entities like lordbuffcloud (CK42X) and duggie162-cpu operate in multiple ecosystems (Flipper Zero/nyanBOX and ESP32/HaleHound), acting as bridges between communities that otherwise remain siloed.

## 25. What This Means for Attribution Analysis

The entity investigation reveals that the HaleHound attribution problem extends beyond a single actor:

- **Primary fault**: ValleyTech (via Ezekiel's basement LLC) for commercial exploitation while obscuring origins
- **Secondary enablers**: Hobbyist contributors (duggie162-cpu, CircuitZ, muffduncan) who improved the project without questioning its attribution chain  
- **Tertiary perpetuators**: Fork/rebrand efforts (houndBEE) that failed to correct the root attribution error
- **Amplifiers**: Cross-pollinators (Talking Saquatch, lordbuffcloud) who spread the project to new audiences without addressing provenance

The "Predatory ESP32 Firmware" description in duggie162-cpu's CYD-INFO repo (a fork of Bruce firmware) suggests at least some community members are aware of the problematic dynamics, even if they continue to participate in the ecosystem.

## 26. Final Verification Notes

All findings presented in Sections 18-22 are:
- **Publicly verifiable** via GitHub APIs, web search indices, and HaleHound release pages
- **Based on immutable evidence**: commit histories, release notes, public profiles
- **Independently confirmable**: Anyone can replicate these checks using the provided GitHub usernames and commit SHAs
- **Contextualized**: Each entity's role is weighed against their actual contributions and network position

The investigation moves beyond speculation to document verifiable relationships and contributions within the HaleHound ecosystem.

---

**[END OF DOCUMENT]**
