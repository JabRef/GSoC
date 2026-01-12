---
title: More Generic Preferences
author: jabref
categories: ["gsoc2026"]
tags: ["project-idea", "size-large"]
---

JabRef's strength is that everything is configurable.
There are more than 100 parameters to tweak.
This is loved and hated by users at the same way.

Two major pain points exist.

1. In the BibTeX (.bib) file, the preferences are stored using a custom format.
2. Some preferences can be configured for each Bib file, but not all.

In this project, two things should be tackled:

1. Rewrite preferences storage in the BibTeX file to JSON [#10371](https://github.com/JabRef/jabref/issues/10371)
2. Offer preferences to be configured in the library. [#8701](https://github.com/JabRef/jabref/issues/8701)

Note that 2 does NOT mean that all preferences should be stored in the library; only the ones the user wants to store.

**Possible Mentors:**

[@koppor](https://github.com/koppor), [@calixtus](https://github.com/calixtus)

**Project size:**

350h (large)
