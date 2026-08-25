---
name: feedback-upsc-source-restriction
description: For UPSC-content research (policy notes etc.), restrict web sources to PIB/NITI Aayog/government sites plus VisionIAS, Drishti IAS, and Vajiram & Ravi only
metadata:
  type: feedback
---

When researching content for this vault's UPSC notes (e.g. building out `notes/GS2/policy/*.md`), the user wants sources restricted to a trusted UPSC-coaching + government set: **Vision IAS, Drishti IAS, Vajiram & Ravi**, and official government sources (**PIB, NITI Aayog**, ministry sites like education.gov.in). Explicit instruction: "do not use any other things" — general web results (Wikipedia, random blogs, Quora, aggregator sites) are out of bounds for this kind of research.

In practice: pass `allowed_domains: ["visionias.in", "drishtiias.com", "vajiramandravi.com", "pib.gov.in", "niti.gov.in", "education.gov.in"]` (extend with other `.gov.in` ministry domains as relevant to the topic) to WebSearch, and only WebFetch pages from those domains. Note that `pib.gov.in` sometimes returns 403 on direct WebFetch — rely on the WebSearch result snippets from PIB in that case rather than dropping the source.

**Why:** These are the sources the user actually studies from and trusts for exam-relevant framing/terminology; general web content risks non-exam-relevant framing or inaccuracy for UPSC purposes.

**How to apply:** Apply this restriction by default for any future "research X for UPSC" / "build a note on policy Y" request in this vault, not just when explicitly repeated. If a topic has no coverage from these sources, say so rather than silently falling back to general web results.
