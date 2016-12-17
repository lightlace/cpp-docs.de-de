---
title: "Blocks"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "Blöcke"
  - "Verbundanweisungen"
  - "Funktionsdefinitionen, Blöcke in Code"
  - "Anweisungen, Verbund"
ms.assetid: be231a92-c712-464e-ae25-a4becb20f7f5
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Blocks
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Eine Sequenz von Deklarationen, Definitionen und Anweisungen, die innerhalb der geschweiften Klammern eingeschlossen sind \(**{ }**\), wird als "Block" bezeichnet. Es gibt zwei Arten von Blöcken in C.  Die "Verbundanweisung" bestehend aus mindestens einer Anweisung \(siehe [Die Verbundanweisung](../c-language/compound-statement-c.md)\) ist eine Art von Block.  Der andere Typ, die "Funktionsdefinition", besteht aus einer Verbundanweisung \(dem Text der Funktion\) und dem zugeordneten "Header" \(dem Funktionsnamen, dem Rückgabetyp und den formalen Parametern\).  Ein Block in anderen Blöcken wird als "geschachtelt" bezeichnet.  
  
 Beachten Sie, dass, während alle Verbundanweisungen in geschweiften Klammern eingeschlossen sind, nicht alles, was innerhalb der geschweiften Klammern eingeschlossen ist, eine Verbundanweisung bildet.  Beispielsweise können die Spezifikationen von Array\-, Struktur\- oder Enumerationselementen zwar innerhalb der geschweiften Klammern angezeigt werden, sie sind jedoch keine Verbundanweisungen.  
  
## Siehe auch  
 [Quelldateien und Quellprogramme](../c-language/source-files-and-source-programs.md)