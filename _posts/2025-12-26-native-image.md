---
title: JabRef components as native images
author: jabref
categories: ["gsoc2026"]
tags: ["project-idea", "size-medium"]
---

JabRef consists of multiple parts: JabKit, JabLS, JabSrv, and JabRef (the GUI).

JabKit is the command-line tool of JabRef offering all the "cool" functionality using a command-line interface. Currently, JabKit is distributed by jpackage and JBang. JPackage creates an installer and portable version. The startup time is way too long for a CLI application. While the installer and portable version include a JDK, JBang downloads the JRE for itself and "just" downloads the Maven artifact jablib to enable execution.

In the Java compiler space, there is the option of [GraalVM and "native image"](https://www.graalvm.org/latest/reference-manual/native-image/). This enables generating an executable file (.exe on Windows) which promises a faster startup.

This GSoC project has two phases:

- Phase 1: Adapt JabKit+jablib to be compatible with `graalvm-native`
- Phase 2: Adapt JabGui to be compatible with `graalvm-native`
- Phase 3: Adapt JabLS to be compatible with `graalvm-native`
- Phase 4: Adapt JabSrv to be compatible to `graalvm-native`

Especially phase 2 might require exchanging libraries in JabRef.

**Why is this a nice project?**

One can learn about fields of Java known to a little group of developers only. One touches areas very new in the Java space. Finally, one can learn about [WASM-compiling of Java](https://github.com/oracle/graal/issues/3391).

**Expected outcomes:**

- jabkit.exe (JabRef's CLI tool)
- jabref.exe (JabRef GUI)
- jabls.exe
- jabsrv.exe

**Skills required:**

- Strong Java-coding skills
- Endurance, because this project might include much trial-and-error

**Possible Mentors:**

[@koppor](https://github.com/koppor), [@InAnYan](https://github.com/InAnYan/), [@calixtus](https://github.com/calixtus)

**Links:**

- Source of JabKit: https://github.com/JabRef/jabref/tree/main/jabkit
- Initial PR trying it https://github.com/JabRef/jabref-koppor/pull/693
- JBang runner for JabKit:  https://github.com/JabRef/jabref/tree/main/.jbang#running-jabkit

**Project size:**

175h (medium)
