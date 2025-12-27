---
title: Improved LibreOffice-JabRef integration
author: jabref
categories: ["gsoc2026"]
tags: ["project-idea", "size-small", "size-medium", "size-large"]
---

**Description:**

JabRef can connect to LibreOffice to offer premier reference management by allowing users to cite library entries directly into the document, and then generate bibliographies based on the cited entries. See [JabRef LibreOffice Integration](https://docs.jabref.org/cite/openofficeintegration).

We have a collection of independent projects available for the LibreOffice/OpenOffice integration feature of JabRef.

1. **BST style support:** Currently, custom styles (JStyles) and CSL styles are supported. In the LaTeX-world, BST styles (specified via `.bst` files) are still popular. JabRef already has BST support, but it is currently not accessible via the UI.

    - Expected deliverable: It should be possible to select a `.bst` file, which is then used for rendering into the LibreOffice document. [Details: [#624](https://github.com/JabRef/jabref/issues/624)]

2. **Improved support for CSL styles:** Support for CSL styles in the LibreOffice integration has been a popular new feature in JabRef that [users look forward to](https://discourse.jabref.org/t/error-when-connecting-to-libreoffice/5431/14?u=subhramit). This project aims to enhance the integration further by introducing **Footnote-based citation support for CSL styles**. Currently, using CSL styles in footnotes of the LibreOffice document causes unexpected behavior, especially for numeric styles. There should be a proper definition of the "global order" of the citations so that they can be used in footnotes. This problem is already solved for JStyles (see a high-level overview [here](https://devdocs.jabref.org/code-howtos/openoffice/order-of-appearance.html)), so the solution needs to be extended/adapted for CSL styles (and BST styles, if project 1 is also undertaken).

    - Expected deliverable: It is possible to use CSL styles in the footnotes of the documents, without any unexpected/broken ordering in the bibliography or numeric citations. [Tracking issue: [#12484](https://github.com/JabRef/jabref/issues/12484)]  

3. **Cross-compatibility with other reference management software**: In case of CSL styles, reference management software like [Zotero](https://www.zotero.org/) and [Mendeley](https://www.mendeley.com/) can read each other's citations in LibreOffice. This is made possible by following a specific format of document annotations, embedding information in CSL JSON. In JabRef, the internal format of references is currently a JabRef-custom format. It should be changed to a format used by Zotero, so that cross-compatibility can be ensured. 
See the discussion at <https://github.com/JabRef/jabref/issues/2146#issuecomment-891432507> for details. This includes:
i) Implementation of that format, ii) Implementation of a converter from the "old" JabRef-Format to the new one. The converter could be implemented within OpenOffice (similar to [JabRef_LibreOffice_Converter](https://github.com/teertinker/JabRef_LibreOffice_Converter?tab=readme-ov-file#jabref_libreoffice_converter)).

    - Expected deliverable: One can seamlessly switch working with LibreOffice documents having citations from Zotero and JabRef.

4. **Seamless citation style type switching:** JabRef in LibreOffice should support auto-updation of references when switching from CSL-based formats to JStyle (or BST)-based formats and back. Currently, if the user messes up and realizes that they had to use another style family, the workaround is to re-cite all entries again with the new style, then refresh the bibliography. This may not be very user-friendly when citation styles need to be updated when submitting papers to different journals (one use-case), or simply because of last-minute change in decisions. For this project, the starting step will be unifying the "reference mark" (document annotation) format for all these style types, so that the entry information can be parsed across styles. This project thus goes very well coupled with Project 1 and Project 3.

    - Expected deliverable: On changing style type (CSL/BST/JStyle), all references in the documents should seamlessly adapt to the new style.

**Skills required:**

- Java, JavaFX

**Possible Mentors:**

[@Siedlerchr](https://github.com/Siedlerchr), [@subhramit](https://github.com/subhramit)

**Project size:**

- **350h (large)**: If (Project 1 + Project 2 + Project 3 + Project 4)

- **175h (medium)**: If (Project 1 + Project 2) **OR** (Project 2 + Project 3) **OR** (Project 1 + Project 3) 

- **90h (small)**: If Project 1 **OR** Project 2 **OR** Project 3

