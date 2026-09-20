# RESEARCH NOTES — Podcast Episode: Digital Rights & Surveillance Technology

> **Project studied:** [HelloZeroNet/ZeroNet](https://github.com/HelloZeroNet/ZeroNet) — 18,768 stars, 2,281 forks
> Decentralized websites using Bitcoin crypto and the BitTorrent network.
> Topics: `anonymity`, `anticensorship`, `bitcoin`, `bittorrent`, `decentralized`, `internet-freedom`, `p2p`, `tor`

---

## 1. PROJECT OVERVIEW

ZeroNet is an open-source, decentralized web platform that uses Bitcoin cryptographic signatures and the BitTorrent network to host and serve websites. Its stated mission:

- **"We believe in open, free, and uncensored network and communication."**
- No single point of failure — a site stays online as long as at least one peer is serving it.
- No hosting costs — sites are served by visitors.
- "Impossible to shut down: It's nowhere because it's everywhere."
- Full Tor network support with `.onion` hidden services instead of IPv4 addresses.
- Password-less BIP32-based authorization (same cryptography as Bitcoin wallets).

**Why it matters for this episode:** ZeroNet is arguably the most ambitious attempt to build censorship-resistant, surveillance-proof web infrastructure from the ground up. It's not just a privacy tool — it's a fundamentally different architecture for how the web can exist, one that eliminates the centralized points where governments and corporations can conduct surveillance or shut down content.

---

## 2. SOCIETAL CONCERNS & ETHICAL TENSIONS

### TENSION A: Absolute Free Speech vs. Protection from Harmful Content

This is the **core ethical fault line** in the decentralized web movement, and it plays out dramatically in ZeroNet's community. See GitHub Issue [#2746 — "Child porn, rape, murder ..."](https://github.com/HelloZeroNet/ZeroNet/issues/2746) (44 comments, 17 reactions).

**The concern:** When you build a network with zero centralized moderation, you also build a network where illegal and harmful content can exist without filtering. A user reported being exposed to child exploitation material, rape, and murder content upon testing the platform — and argued that this *undermines* the legitimate privacy mission of the technology.

**Key quote from the issue author (IGLOU-EU):**
> "No censoring at all, is not a good idea... This is not the purpose of this anonymous tech and, furthermore, I think it works against it... The engineer is not responsible for the way people are using of their tech, but if it can fix it but don't do it, he is responsible."

**The counter-argument (from community members):**
- Prohibition doesn't work — illegal communities are hard to access even for law enforcement.
- Modality vs. censorship are different things — community-based moderation can exist without centralized control.
- "It's impossible to harm other by the simple act of sharing a sequence of 0s and 1s over the internet."
- Centralized moderation (YouTube, Facebook, Twitter) is worse.

**Podcast angle:** This isn't hypothetical. It's an active, unresolved debate happening right now in the code and governance of real decentralized systems. The question is: **Can you have absolute free speech *and* protect people from harm? Or does absolute free speech inevitably become a weapon against the vulnerable?**

### TENSION B: The Responsibility Paradox for Tool Builders

Closely related to Tension A, but worth its own discussion:

- The original poster argued: *"The engineer is not responsible for the way people are using of their tech, but if it can fix it but don't do it, he is responsible."
- This is the **weaponized tool dilemma** — the same technology that protects journalists in authoritarian regimes also protects child exploiters. The tool is neutral, but its effects are not.
- **Podcast angle:** Where does responsibility lie? With the builder? The user? The platform? Should there be a "low censoring procedure" — not GAFAM-style censorship, but community-driven content filtering? One commenter proposed a layered moderation system:
  1. **Passive social moderation** — content sorted by active seeder count (fewer seeders = less visibility = fewer people exposed to harmful content).
  2. **Community blocklists** — trusted community members manage and maintain blocklists that users can opt into.
  3. **Personal moderation** — individual users choose what to view.
  - *"AT NO POINT SHOULD WE INTRODUCE A SINGLE FORM OF CENTRALISED POWER — ONCE THIS STEP IS TAKEN, YOU CANNOT GO BACK."\*

### TENSION C: Decentralization vs. Governance — The EpixNet Transition

GitHub Issue [#2879 — "ZeroNet Transition to EpixNet Development"](https://github.com/HelloZeroNet/ZeroNet/issues/2879) reveals a seismic shift:

- The **original developer has departed** the project.
- A new entity, **EpixNet**, is taking over development with a stated goal of building "a more modern, scalable, and long-term sustainable system."
- The new direction explicitly includes: **"building a business model and monetization opportunities"** and **"fixing security vulnerabilities."

**Why this matters for the podcast:** This is the eternal tension in anti-surveillance technology — **can a tool designed to resist corporate and state power be sustained by corporate and state power?** The original ZeroNet was a pure, idealistic project with no monetization. The new direction is toward enterprise integration, business models, and sustainability. But any business model introduces:

- **Centralization risk** — who controls the enterprise version?
- **Surveillance risk** — does a monetized ZeroNet inevitably become a surveilled ZeroNet?
- **Abandonment of anti-corporate principles** — or are they compatible with sustainability?

### TENSION D: The DNS Paradox

From community discussion in issue #2857:

- One developer argued: *"by its nature, any DNS is centralized (even if there's no singular authority, there has to be consensus) and one of valuable features of 0net for me is ability to work offline and in (partially) isolated networks."
- Another proposed replacing DNS with a built-in blockchain — a "ZeroNetwork chain" that provides Bitcoin addresses representing zites (sites) containing name resolution data.
- **The paradox:** To make the network more user-friendly and scalable, you may need to reintroduce the very centralization (DNS, name resolution, trusted authorities) that the network was designed to eliminate.

**Podcast angle:** This mirrors a broader pattern in privacy tech — **the usability/surveillance tradeoff**. Every improvement in ease-of-use seems to require a small concession to centralization. How much centralization can an anti-surveillance system tolerate before it becomes a surveillance system?

### TENSION E: Law Enforcement & the "Bait" Problem

One commenter raised a chilling observation:

> *"Let's not forget that the authorities use illegal content to bait criminals as well as subvert legit communities."

This is the **crime/fraud baiting** problem: in a truly anonymous, unmoderated network, law enforcement doesn't just *investigate* crime — they can *create and deploy* illegal content to trap users or discredit the network. This means:

- Unmoderated networks are not just havens for criminals — they are **attack surfaces** for state actors.
- The lack of moderation that free-speech absolutists celebrate is the same lack of moderation that **authoritarian surveillance agencies exploit.**
- **Podcast angle:** The absence of content moderation on decentralized platforms doesn't just enable harm — it *invites state manipulation.* This is a critical and under-discussed dimension of the surveillance debate.

---

## 3. KEY THEMES FOR PODCAST EXPLORATION

### Theme 1: The Double-Edged Sword of Anonymity
Anonymity protects the vulnerable (whistleblowers, dissidents, abuse survivors) and the predatory (child exploiters, fraudsters, authoritarian agent provocateurs). Can we design systems that preserve anonymity for the innocent while denying it to the malicious? Or is true anonymity indivisible?

### Theme 2: Who Owns the Platform When It Has No Owner?
ZeroNet's original governance structure was leaderless and community-driven. The EpixNet transition forces the question: **Can a genuinely decentralized project be sustained without centralizing control?** What does "ownership" even mean for a network that's "nowhere because it's everywhere"?

### Theme 3: The Moderation Middle Ground
The community proposed a three-tier moderation system (seeder-based sorting, community blocklists, personal moderation) that avoids both GAFAM-style top-down censorship and total anarchy. Is this viable? Has any decentralized platform successfully implemented it? What are the failure modes?

### Theme 4: Surveillance Tech as a Tool of the State
ZeroNet was built to resist surveillance. But the same infrastructure that resists corporate surveillance also resists *criminal* investigation. Meanwhile, law enforcement can use the *absence* of moderation to their advantage. **Who really benefits from an unmoderated, fully anonymous web?** The dissident in Iran or the FBI agent?

### Theme 5: The Sustainability Paradox
Pure anti-surveillance tech struggles to sustain itself. Commercialization introduces the very centralized power structures it was designed to resist. **Is there a sustainable path between idealism and compromise?** Or is the persistence of surveillance-proof technology inherently incompatible with the economic logic of the modern internet?

### Theme 6: The "Engineer's Responsibility" Question
"If it can fix it but don't do it, he is responsible." Should software engineers building privacy tools bear some responsibility for how their tools are used? This is the **weapons designer's dilemma** — the same question that applies to encrypted messaging, cryptocurrency, and AI.

---

## 4. REFERENCE LINKS

- **Repository:** https://github.com/HelloZeroNet/ZeroNet
- **Website:** https://zeronet.io
- **Original issue on harmful content:** https://github.com/HelloZeroNet/ZeroNet/issues/2746
- **EpixNet transition announcement:** https://github.com/HelloZeroNet/ZeroNet/issues/2879
- **Organization migration discussion (governance):** https://github.com/HelloZeroNet/ZeroNet/issues/2859
- **Content encryption discussion:** https://github.com/HelloZeroNet/ZeroNet/issues/252
- **Rogue peer protection discussion:** https://github.com/HelloZeroNet/ZeroNet/issues/1817
- **Related privacy projects found during research:**
  - `pluja/awesome-privacy` (19,809 stars) — curated privacy/resilience tools
  - `searx/searx` (13,551 stars) — privacy-respecting metasearch engine
  - `FreeTubeApp/FreeTube` (21,954 stars) — open-source YouTube app for privacy
  - `simeononsecurity/eye-spy` — passive surveillance detector (BLE/WiFi)
  - `soyboi1312/all-cameras-are-beacons` — counter-surveillance firmware for ESP32
  - `HelloZeroNet/ZeroNet` — decentralized websites (Bitcoin + BitTorrent + Tor)

---

## 5. SOURCES & METHODOLOGY

- Repository details, issues, and community discussions pulled directly from GitHub via the GitHub API.
- All quotes are from actual GitHub comments on the cited issues.
- Research conducted on 2026-09-18.
- Forked locally to `bro26man-hash/ZeroNet` for reference.

---

*Notes compiled for podcast research. All opinions and quotes belong to the original authors.*
