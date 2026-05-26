# ValleyTech Custom Solutions — Full Investigation Report

**Author:** r13xr13
**Date:** May 2026
**Status:** Published

---

## Table of Contents

1. Background & Motivation
2. The RF Reaper Incident — Chronology
3. The Evidence — Documented Timeline
4. Illya's Testimony — Full Transcript Summary
5. ValleyTech's Business Profile
6. Owner Identity Investigation
7. Pricing & Profit Analysis
8. The Community Reaction
9. The Broader Pattern
10. Conclusion & Demands

---

## 1. Background & Motivation

I run a small technical analysis operation. I reverse-engineer hardware, study firmware, and occasionally document things that bother me. I had no intention of getting involved in the ValleyTech situation until I saw what happened to Illya.

I was already working on the HaleHound analysis when I learned about the RF Reaper story. A friend sent me a link to Illya's video and said, "You should look at this." I watched a 15-year-old kid calmly explain how he lost over a thousand dollars because someone he trusted told him it was a good business decision. And the community response was not "we should help this kid" — it was "he should not have leaked the files" and "he should not have had the link."

Something is wrong with that picture.

I started digging. I pulled business records. I watched hours of YouTube videos. I read through the transcripts. And the more I looked, the clearer the pattern became.

This is not a story about a single bad transaction. It is a story about how platform, age, and community dynamics let one person shift all the risk onto a kid while keeping all the benefit for himself.

---

## 2. The RF Reaper Incident — Chronology

### Phase 1: The Setup

In January 2026, the RF Reaper was a prototype. Bruce Dev Team had designed it but apparently lacked the manufacturing capital. Khalil (ValleyTech) had the design files and an Elecrow manufacturing relationship. Illya (Arch Labs) had a small but growing electronics store and a YouTube channel documenting his builds.

Khalil contacted Illya and offered him a private pre-order link on Elecrow for the RF Reaper. The device was described as an all-in-one cybersecurity tool featuring:

- ESP32-S3 microcontroller
- CC1101 sub-1GHz transceiver
- NRF24L01+ 2.4GHz radio
- NEO-6M GPS module
- RC522 NFC module
- TFT LCD display
- 18650 battery support
- SMA antenna connectors

Khalil told Illya to buy 10 units. He explained that the boards would sell for $250 and would sell out immediately. He positioned it as a guaranteed win — the smartest business decision Illya could make.

Illya placed the order. He paid $865 for the boards, $60 for shipping, and $130 in tariffs. Total: approximately $1,055.

### Phase 2: The Delivery

When the boards arrived, they were not complete products. They were bare PCBs with only basic components populated. The following items were missing:

- **CC1101 module** — the single most expensive and most critical RF component
- **GPS module** — NEO-6M, not included
- **18650 battery** — no power source
- **TFT display** — no screen
- **Antennas** — no SMA or PCB antennas
- **SMA connectors** — no RF connectors

What Illya received was a partially assembled board that could not function as a complete product without significant additional parts and labor.

### Phase 3: The Fallout

Illya contacted Elecrow for a resolution. Elecrow offered a $75 refund. Not a replacement. Not a credit. Seventy-five dollars on an $865 order.

Illya contacted Khalil for help. According to Illya's testimony, the response was not what he expected. Instead of assistance, he found himself being blamed for the situation — criticized for having the Gerber files that Khalil himself had sent, accused of mishandling something he never asked to be part of.

Because Khalil controlled the narrative and had the larger platform, the community's interpretation of events was shaped by his version.

### Phase 4: The Aftermath

Illya had spent over $1,000 and was left with 10 incomplete boards. To salvage the situation, he purchased the missing parts himself and assembled the units by hand. After parts and labor, each completed unit cost him approximately $110 — significantly more than the $65 he originally paid per unit.

Meanwhile, ValleyTech's Elecrow store continued selling RF Reaper boards, and ValleyTech promoted the Bruce Dev Team budget version at $80 — less than Illya's cost to complete a single unit.

---

## 3. The Evidence — Documented Timeline

| Date | Event | Source |
|---|---|---|
| Jan 2026 | Khalil contacts Illya with private RF Reaper link | Illya video testimony |
| Jan 2026 | Illya orders 10 units from Elecrow ($865) | Order confirmation |
| Feb 2026 | Boards arrive — incomplete, missing key components | Illya video unboxing |
| Feb 2026 | Elecrow offers $75 refund | Illya testimony |
| Feb 2026 | Illya contacts Khalil — receives blame, not help | Illya video |
| Feb 2026 | Illya posts video documenting the situation | YouTube (Arch Labs) |
| Mar 2026 | Illya spends ~$110/unit to complete boards | Parts receipts |
| Jun 2026 | Illya posts second video with full story | YouTube (Arch Labs) |

---

## 4. Illya's Testimony — Full Transcript Summary

In June 2026, Illya published a 13-minute video titled *"ValleyTechSolutions & Bruce-Dev Team SCAMMERS!"* on his channel "Adventures of Illya." The following is a summary of his account.

**On how the deal started:**
Khalil reached out directly. He sent Illya a private Elecrow link that was not publicly available. He told Illya to buy 10 units and that they would sell for $250. Illya trusted him because he seemed like a leader in the community.

**On what went wrong:**
The boards arrived without the CC1101 module — the main RF chip — and without GPS, battery, screen, antennas, or connectors. They were not functional as RF Reapers.

**On the Gerber file issue:**
Khalil sent Illya the full design files — Gerbers, BOM, STL. These were supposed to be closed source. When the situation went bad, Illya was accused of having files he should not have had — even though Khalil sent them to him.

**On being told he was like family:**
Khalil told Illya he was like his "bigger brother" in the community. This language of mentorship and family was used to build trust that was then exploited.

**On the outcome:**
Illya now has 10 units he had to complete himself, at a cost higher than ValleyTech's retail price. He has no way to sell them competitively. He is holding inventory he cannot move because ValleyTech announced a cheaper version.

---

## 5. ValleyTech's Business Profile

### Company Information

| Field | Value |
|---|---|
| Entity Name | ValleyTech Custom Solutions LLC |
| Address | 7107 Ayers Meadow Lane, Springfield, VA 22150 |
| Phone | (571) 424-6558 |
| Email (Shopify) | alarqawi@valleytechsolutions.tech |
| Registered | ~June 2024 |
| GitHub Created | August 18, 2024 |

### Online Presence

- **Website:** valleytechsolutions.tech
- **Shopify Store:** valleytechsolutions.tech (via Shopify)
- **YouTube:** ~96,000 subscribers, 850+ videos, ~6M views
- **Elecrow:** Partner reseller
- **GitHub:** github.com/valleytechsolutions

### Products & Services

- Flipper Zero accessories and modifications ($65 RGB mod)
- M5Stack and ESP32 boards
- Bruce Dev Team firmware tools and devices
- Custom PCB design and manufacturing (via Elecrow)
- Mail-in modification services
- RF Reaper boards (from $80)

### Their Self-Description

From their Elecrow storefront:
> *"We are Valleytech Custom Solutions, an ethical hacking, pen-testing, tech repair, data recovery, and IOT company based in Northern Virginia."*

From their Nextdoor post:
> *"Hello! My name is Khalil and I run Valleytech Custom Solutions. We are an educational based company primarily focused on Tech Repair and Tech Solutions from basic computer repair, to Network Solutions, to hardware and software testing, to gamepad repair."*

---

## 6. Owner Identity Investigation

### What He Calls Himself

- **"Khalil"** — Used on Nextdoor, YouTube, and most public interactions
- **"Your Pal Kal"** — An informal moniker used in videos and community posts
- **"Khalil Alarqawi"** — This surname appears on the Shopify store's email address (alarqawi@...)

### What Others Claim

Some community members claim the owner's name is **Khalid "Far" Chaudhry**. This has not been verified. A Nextdoor post from the owner uses the name "Khalil" without a surname.

### What Public Records Show

The address 7107 Ayers Meadow Lane, Springfield, VA 22150 is a residential property. The LLC registration for ValleyTech Custom Solutions lists the organizer, but the exact name on file requires pulling full Virginia business records.

### The Email Discrepancy

The email on the Shopify refund policy is alarqawi@valleytechsolutions.tech. The domain valleytechsolutions.tech was registered through Wild West Domains, LLC (GoDaddy subsidiary) on May 14, 2024. The registration is marked as private, concealing the registrant's identity.

**Note:** The discrepancy between "Chaudhry" (claimed by some community members) and "Alarqawi" (on the business email) remains unresolved. I have not been able to confirm the owner's legal full name. I will update this section if I obtain verifiable public records.

---

## 7. Pricing & Profit Analysis

### What Illya Paid

| Item | Cost |
|---|---|
| 10 RF Reaper boards (Elecrow) | $865.00 |
| Shipping | $60.00 |
| Import tariffs | $130.00 |
| **Total paid to Elecrow** | **$1,055.00** |
| Elecrow refund | -$75.00 |
| **Net loss to Illya** | **$980.00** |
| Additional parts to complete 10 units | ~$1,100.00 |
| **Total Illya's cost** | **~$2,080.00** |

### What ValleyTech Charges

- RF Reaper (main version): varies
- Bruce Dev Team budget version: ~$80/unit

### The Implication

Illya paid approximately $208 per completed unit ($2,080 total for 10 working units).

ValleyTech's Bruce Dev Team version retails for $80.

Illya cannot sell his units for what they cost him. ValleyTech can undercut him because they did not carry the inventory risk, the tariff cost, or the parts cost. ValleyTech leveraged Illya as a beta manufacturer and then moved on.

---

## 8. The Community Reaction

### What Happened to Illya

Instead of receiving support, Illya was criticized for:
- Having the Gerber files (which Khalil sent him)
- Making the situation public
- Not understanding business
- "Leaking" closed-source files

The people who should have been asking "why did a 15-year-old get set up to lose $1,000?" were instead asking "why did he have those files?"

### What Happened to Me (r13xr13)

When I pointed out what had happened, I was:
- Accused of starting drama
- Told to stay out of it
- Blocked by community members
- Quietly pushed out of conversations

I am now effectively blackballed from the cybersecurity hardware community for defending a 15-year-old who got taken advantage of.

### Why This Pattern Matters

This is how vulnerable people get isolated in niche communities. The person with the platform defines reality. Anyone who contradicts the platform holder becomes the problem. Justice becomes about who can tell the story loudest, not about what actually happened.

---

## 9. The Broader Pattern

### Not an Isolated Incident

The RF Reaper situation fits a pattern of behavior:

1. **Build trust through mentorship language** — "I'm your bigger brother in this community"
2. **Leverage that trust to extract value** — "Buy 10 units, it's the smartest thing you can do"
3. **Shift all risk to the other party** — Illya paid, Illya received bad boards, Illya paid to fix them
4. **Change the story when things go wrong** — "You were never supposed to have that link"
5. **Use platform advantage to control the narrative** — 96K subs vs. small channel
6. **Blame the victim** — For having files, for speaking up, for "not understanding business"
7. **Silence dissenters** — Anyone who questions gets labeled as drama

### The Open Source Problem

ValleyTech presents itself as an education-focused company while:
- Selling closed-source firmware
- Keeping Gerber files private
- Partnering exclusively with specific manufacturers
- Using community-created designs for commercial purposes

This is not open source. It is not educational. It is profiteering dressed up as community service.

---

## 10. Conclusion & Demands

### Demands

1. **ValleyTech should make Illya whole** — Refund the full cost of the boards plus the additional parts Illya had to purchase. This is approximately $2,080.

2. **ValleyTech should publicly acknowledge what happened** — Not a legal admission of liability, but at minimum a statement that Illya was put in an unfair position and that the outcome was not his fault.

3. **The community should reconsider** — Anyone who silenced or blocked people for speaking up about this should ask themselves whether they helped or harmed the situation.

### Final Statement

I have not posted this to harass anyone. I am not asking anyone to harass anyone. If ValleyTech makes this right, I will update this report to reflect that.

But I will not delete this repository. And I will not apologize for standing up for a kid who got taken advantage of.

The only thing necessary for the triumph of evil is for good people to do nothing. I am done doing nothing.

---

*For questions, evidence submissions, or corrections: open an issue or PR on this repository.*

*If you are Illya and want changes or removal of any details: contact me and I will comply immediately.*
