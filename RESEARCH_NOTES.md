# 🎙️ Podcast Research Notes: ZeroNet — Digital Rights, Surveillance & the Uncensorable Web

> **Repository:** [HelloZeroNet/ZeroNet](https://github.com/HelloZeroNet/ZeroNet)  
> **Forked to:** [bro26man-hash/ZeroNet](https://github.com/bro26man-hash/ZeroNet)  
> **Stars:** 18,769 | **Forks:** 2,281 | **Language:** JavaScript (Python backend)  
> **License:** Other (proposed dual-license: GPLv3+ / Lax)  
> **Topics:** `anonymity` `anticensorship` `bitcoin` `bittorrent` `decentralized` `internet-freedom` `p2p` `tor` `web`

---

## 1. Project Overview

ZeroNet is a decentralized web platform that uses **Bitcoin cryptography** and the **BitTorrent network** to create websites that are:

- **Impossible to shut down** — There is no single point of failure; a site remains online as long as at least one peer is serving it.
- **Censorship-resistant** — No central authority can remove content because there's no central server.
- **Anonymous** — Full Tor network support with `.onion` hidden services instead of IPv4 addresses.
- **Free to host** — Sites are served by visitors; there are no hosting costs.
- **Cryptographically authenticated** — Site ownership is proven via BIP32 (Bitcoin) key pairs; content integrity is verified via SHA-512 hashes and signatures in `content.json`.

**Core philosophy (from the README):**
> *"We believe in open, free, and uncensored network and communication."*
> *"Impossible to shut down: It's nowhere because it's everywhere."*

---

## 2. Key Features Relevant to Surveillance & Privacy

| Feature | Privacy/Surveillance Implication |
|---|---|
| **BitTorrent-based distribution** | No central server to monitor, subpoena, or shut down. Content persists as long as even one peer seeds it. |
| **Tor / .onion support** | Full anonymity for both publishing and browsing. No IP address exposure. |
| **Bitcoin-key identity (BIP32)** | Password-less authentication tied to Bitcoin wallets. Pseudonymous but not fully anonymous. |
| **P2P data synchronization** | Built-in SQL server with peer-to-peer sync — no centralized database to compromise. |
| **TLS encrypted connections** | Transport-level encryption between peers. |
| **Real-time updated sites** | Push-based updates — no need to poll a central server, reducing metadata leakage. |
| **No logging architecture** | The protocol itself doesn't require any server-side logging. |

---

## 3. Societal Concerns & Ethical Tensions

### 3.1 The Censorship Dilemma — "No Censoring at All"

**Source:** [Issue #2746 — "Child porn, rape, murder ..."](https://github.com/HelloZeroNet/ZeroNet/issues/2746) (44 comments, 17 reactions, still open)

This is the **single most important ethical discussion** in the ZeroNet community and directly relevant to your podcast.

**The argument against total uncensored speech:**
- User **IGLOU-EU** tested ZeroNet and was exposed to "unacceptable content" (CSAM, violence, etc.).
- They argue that **total absence of moderation is not a feature** — it works against the rights and mental health of users who stumble upon horrific content.
- They propose a **"low censorship" methodology** — not GAFAM-style corporate censorship, but a **community-based moderation system** (e.g., content rating, review bombing resistance) that protects users while preserving free speech.
- Key quote: *"The engineer is not responsible for the way people use their tech, but if it can fix it but doesn't, he is responsible."*

**The counter-argument (from the community):**
- **deathtrip** argues that the user "actively searched" for illegal content and that law enforcement itself struggles to find these communities — suggesting the concern is overblown.
- **gqgs** argues that "sharing a sequence of 0s and 1s" cannot harm anyone, and that existing tools (block lists, moderated sites, text-only sites) are sufficient.
- **rebelloV** counters that moderation ≠ censorship: *"I formerly used this network, and I would like to [use it again]. How can we be ruining it? We are simply expressing our opinions to avoid people getting mentally scarred or hurt."*

**Podcast angles:**
- 🔹 **The "Harmful Speech" problem for decentralized systems:** Can you build a censorship-resistant network without it becoming a haven for the worst content? Is "optionality" (letting users choose their own filters) sufficient?
- 🔹 **The responsibility of toolmakers:** When does a developer's ethical duty extend beyond "just building the tool"? Does the resistance argument ("code is speech") have limits?
- 🔹 **Community moderation vs. algorithmic moderation:** ZeroNet's proposal for community-based content rating is an alternative to both GAFAM moderation and total anarchy. Could this model scale? What are the failure modes (review bombs, coordinated abuse)?

### 3.2 The Creator Disappearance / Project Sustainability Crisis

**Source:** [Issue #2749 — "Where did the ZeroNet creator go?"](https://github.com/HelloZeroNet/ZeroNet/issues/2749) (41 comments, 18 reactions, still open)

- The original creator (**Tamas** / **San》
- Community members worry he may have been **imprisoned or killed** for his work on censorship-resistant technology. One commenter referenced the suspicious death of Sam emergency" if the creator was detained.
- Some community members believe the project is **economically unviable** — no meaningful donations, no business model, no site-owner revenue.
- The project has **significant technical debt**: it depends on obsolete Python 3.7, unmaintained dependencies (merkletools), and has no PyPI package. One maintainer (leycec) had to remove it from Gentoo entirely.

**Podcast angles:**
- 🔹 **The personal risk of building anti-surveillance tech:** What happens to the people who build tools that threaten state surveillance? The creator's disappearance is a chilling reminder that this work has real-world consequences.
- 🔹 **Sustainability of open-source civil liberties tools:** If the best tools are maintained by sole volunteers with no funding, what does that mean for the future of digital rights? Should there be public funding models for this work?
- 🔹 **The "abandonment" problem:** Even successful open-source projects (18K+ stars) can stall if they can't attract maintainers. What does it mean for critical infrastructure that depends on volunteer labor?

### 3.3 The Licensing & Governance Debate

**Source:** [Issue #2273 — "Contributor Agreement for License Change"](https://github.com/HelloZeroNet/ZeroNet/issues/2273) (588 comments, still open)

- The project's license is currently **"Other" / NOASSERTION** — unclear and unstated in many contexts.
- There's an active (though slow-moving) debate about changing to a **dual license: GPLv3+ / Lax**.
- 588 comments suggest deep community disagreement about what the right license should be.
- The "Lax" license component would allow **proprietary use** of the code, which some argue would enable corporations to exploit the work without contributing back.

**Podcast angles:**
- 🔹 **Copyleft vs. permissive licensing in the civil liberties space:** If a censorship-resistant tool goes proprietary, who controls the future? Should open-source anti-surveillance tech be required to stay open?
- 🔹 **Governance of decentralized projects:** How do you make decisions about a project that is itself about decentralization? The licensing debate reveals tensions between freedom (GPLv3) and pragmatism (Lax).

### 3.4 The Overlay Network Vision

**Source:** [Issue #1820 — "ZeroNet as a platform for overlay networks"](https://github.com/HelloZeroNet/ZeroNet/issues/1820) (9 comments, still open)

- User **klueq** proposed using ZeroNet as a **library** to build arbitrary overlay networks — e.g., a distributed books catalogue with ~1M nodes, <1KB messages, no admin, no special keys.
- This reveals that ZeroNet's architecture could be the **foundation for a generalized privacy layer** — not just websites, but any P2P application.

**Podcast angles:**
- 🔹 **From "uncensorable websites" to "uncensorable internet":** If ZeroNet (or something like it) could underpin all P2P communication, what does that mean for the future of surveillance? Could it make mass surveillance economically impossible?
- 🔹 **The dual-use problem:** The same architecture that enables free speech in Iran also enables CSAM distribution. There's no technical solution to this — only social/policy ones.

---

## 4. Broader Context: ZeroNet in the Privacy-Tech Ecosystem

ZeroNet doesn't exist in isolation. It's part of a broader ecosystem of decentralization and anti-surveillance tools:

| Project | Relationship to ZeroNet | Key Difference |
|---|---|---|
| **Tor** | ZeroNet uses Tor for anonymity | Tor is a browser/proxy; ZeroNet is a full web hosting platform |
| **IPFS** | Alternative decentralized web | IPFS uses content-addressed storage; ZeroNet uses Bitcoin keys + BitTorrent |
| **Freenet** | Alternative censorship-resistant network | Freenet is more mature but slower; ZeroNet is more web-like |
| **LBRY / Odysee** | Decentralized content hosting | LBRY focuses on video/content monetization; ZeroNet is general-purpose |
| **Cloak** (4,088 ⭐) | Censorship circumvention tool | Cloak evades DPI detection; ZeroNet resists takedown via distribution |
| **Lantern** (17,802 ⭐) | Censorship circumvention proxy | Lantern is a proxy/gateway; ZeroNet is a hosting/network layer |

---

## 5. Podcast Episode Angles — Recommended Topics

### 🎙️ Core Narrative
**"The Uncensorable Web: What ZeroNet Teaches Us About the Future of Digital Rights"**

### Suggested Segments

1. **"The Promise"** — How ZeroNet works (Bitcoin crypto + BitTorrent = no kill switch for speech)
2. **"The Dark Side"** — What happens when you remove all moderation (Issue #2746)
3. **"The Privacy Paradox"** — Anonymity for journalists and dissidents vs. anonymity for predators
4. **"The Creator's Fate"** — What happens to the people who build these tools? (Issue #2749)
5. **"Who Owns the Code?"** — The licensing battle and what it means for the future of open-source civil liberties tech (Issue #2273)
6. **"The Bigger Picture"** — ZeroNet's overlay network vision and what it could mean for mass surveillance

### Discussion Questions for Guests
- Is "total free speech" a feature or a bug in a decentralized system?
- Should there be a technical filter for illegal content, or is any filtering a slippery slope?
- Can a tool that's useful for dissidents in China also be used by criminals — and does that matter?
- What would a sustainable funding model for anti-surveillance open-source look like?
- If ZeroNet succeeded at scale, would mass surveillance become economically unfeasible — or would it just move underground?

### Key Quotes for the Episode
> *"We believe in open, free, and uncensored network and communication."* — ZeroNet README

> *"No censoring at all is not a good idea... I don't want a censored web, but no censoring at all is unacceptable too."* — IGLOU-EU, Issue #2746

> *"I am afraid that he was imprisoned or killed. Let at least someone who knows something about him write."* — Community member, Issue #2749

> *"Impossible to shut down: It's nowhere because it's everywhere."* — ZeroNet README

---

## 6. References & Further Reading

- **Issue #2746** (CSAM/moderation debate): https://github.com/HelloZeroNet/ZeroNet/issues/2746
- **Issue #2749** (Creator disappearance): https://github.com/HelloZeroNet/ZeroNet/issues/2749
- **Issue #2273** (Licensing/governance): https://github.com/HelloZeroNet/ZeroNet/issues/2273
- **Issue #1820** (Overlay networks): https://github.com/HelloZeroNet/ZeroNet/issues/1820
- **Issue #2823** (Spam/hostile forks): https://github.com/HelloZeroNet/ZeroNet/issues/2823
- **ZeroNet website**: https://zeronet.io
- **ZeroNet docs**: https://zeronet.io/docs/
- **r/zeronet community**: https://www.reddit.com/r/zeronet/

---

*Notes compiled from GitHub research on HelloZeroNet/ZeroNet — forked for podcastPrep.*
