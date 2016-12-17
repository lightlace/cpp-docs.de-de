---
title: "&#39;&lt;Elementname&gt;&#39; ist mehrdeutig, da in &lt;Typ&gt; &#39;&lt;Typname&gt;&#39; mehrere Arten von Membern mit diesem Namen vorhanden sind."
ms.custom: na
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "bc31429"
  - "vbc31429"
helpviewer_keywords: 
  - "BC31429"
ms.assetid: fdc92c16-934d-47c0-9c44-332cbd58b73b
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;Elementname&gt;&#39; ist mehrdeutig, da in &lt;Typ&gt; &#39;&lt;Typname&gt;&#39; mehrere Arten von Membern mit diesem Namen vorhanden sind.
Ein Ausdruck greift auf ein Programmierelement zu, das in einer Klasse, in einer Struktur, in einem Modul oder in einer Schnittstelle definiert ist, die bzw. das mehrere Member mit demselben Namen enthält.  
  
 Die wahrscheinlichste Ursache für diesen Fehler ist die *Berücksichtigung der Groß\-\/Kleinschreibung*. Bei Visual Basic\-Namen wird die Groß\-\/Kleinschreibung nicht berücksichtigt, was bedeutet, dass Sie die Namen an verschiedenen Stellen im Code hinsichtlich der Groß\-\/Kleinschreibung unterschiedlich schreiben können. Wenn Sie z. B. eine Variable namens `XYZ` definieren und später als `xyz` darauf zugreifen, betrachtet der Compiler diese beiden Namen als äquivalent.  
  
 Bei anderen Sprachen wie [C\#](../Topic/C%23.md) und [Visual C\+\+](../top/visual-cpp-in-visual-studio-2015.md) wird die Groß\-\/Kleinschreibung jedoch berücksichtigt. In einer Sprache mit Berücksichtigung der Groß\-\/Kleinschreibung gelten `XYZ` und `xyz` nicht als identisch. Daher kann eine Klasse, die in einer solchen Sprache geschrieben wurde, eine Variable namens `XYZ` sowie eine Eigenschaft namens `xyz` definieren. Die Common Language Runtime \(CLR\) behält die Berücksichtigung der Groß\-\/Kleinschreibung in Assemblys bei. Wenn eine Visual Basic\-Anwendung jedoch auf eine Assembly mit den Namen `XYZ` und `xyz` zugreift, werden sie mit demselben Namen angezeigt.  
  
 **Fehler\-ID:** BC31429  
  
### So beheben Sie diesen Fehler  
  
1.  Wenn Sie die Kontrolle über den Quellcode des definierenden Typs haben, sollten Sie die Umbenennung der Member erwägen, damit sie sich nicht nur durch die Groß\-\/Kleinschreibung unterscheiden. Dies ist ggf. nicht möglich, wenn der definierende Typ bereits veröffentlicht wurde und von anderen Anwendungen verwendet wird.  
  
2.  Wenn Sie die Member im definierenden Typ nicht umbenennen können, entfernen Sie das genannte Programmierelement aus dem Code. Sie können nicht auf Elemente zugreifen, die für Visual Basic mehrere Definitionen zu besitzen scheinen.  
  
## Siehe auch  
 [Declared Element Names](../Topic/Declared%20Element%20Names%20\(Visual%20Basic\).md)   
 [Problembehandlung bei Variablen](../Topic/Troubleshooting%20Variables%20in%20Visual%20Basic.md)   
 [Common Language Runtime](../Topic/Common%20Language%20Runtime%20\(CLR\).md)