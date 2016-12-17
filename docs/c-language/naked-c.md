---
title: "Naked (C)"
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
  - "Epilogcode"
  - "naked-Schlüsselwort [C]"
  - "naked-Schlüsselwort [C], Speicherklassenattribut"
  - "Prologcode"
ms.assetid: 23b1209b-93ba-46ad-a60f-2327c1933eaf
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# Naked (C)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Das naked\-Speicherklassenattribut ist eine Microsoft\-spezifische Erweiterung der Programmiersprache C.  Der Compiler generiert Code ohne Prolog\- und Epilogcode für Funktionen, die mit dem naked\-Speicherklassenattribut deklariert werden.  Naked\-Funktionen sind hilfreich, wenn Sie eigene Prolog\-\/Epilogcodesequenzen mithilfe des Inlineassemblercodes schreiben müssen.  Naked\-Funktionen sind für das Schreiben von virtuellen Gerätetreibern hilfreich.  
  
 Spezielle Informationen zur Verwendung des naked\-Attributs finden Sie unter [naked\-Funktionen](../c-language/naked-functions.md).  
  
 **END Microsoft\-spezifisch**  
  
## Siehe auch  
 [C\-Speicherklassenattribute \(erweitert\)](../c-language/c-extended-storage-class-attributes.md)