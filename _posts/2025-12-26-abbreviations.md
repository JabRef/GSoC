---
title: Improved Journal Abbreviations
author: jabref
categories: ["gsoc2026"]
tags: ["project-idea", "size-small"]
---

Currently, JabRef has a single list of journal abbreviations. This list is a combined list of the `.csv` files at <https://github.com/JabRef/abbrv.jabref.org/tree/main/journals>.
Instead of the dropdown of JabRef should not show a single "JabRef built in list", but should show the various lists we offer: built-in lists, external lists, custom lists. 
Then, one can enable and disable with a click. This eases the users to find issues in abbreviation lists and allows users to customize the lists according to their field (e.g., physics, information science, ...).

Fore more context, see: <https://github.com/JabRef/jabref/issues/12364> and list of all abbreviation issues: <https://github.com/jabref/jabref/issues?q=is%3Aissue%20state%3Aopen%20label%3A%22component%3A%20journal%20abbreviations%22>. Please also check existing pull requests and comments on them.

**Skills required:**

- Java, JavaFX

**Expected Outcome:**

A UI view which allows selecting/including journal abbreviations by category. 

**Possible Mentors:**

[@calixtus](https://github.com/calixtus), [@koppor](https://github.com/koppor)

**Project size:**

- 90h (small) to medium
