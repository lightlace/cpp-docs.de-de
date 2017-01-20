---
title: "&#220;bersetzung: Diagnose"
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
ms.assetid: 3730ca7c-0147-452d-bd4a-6a1e97e9793e
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# &#220;bersetzung: Diagnose
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**ANSI 2.1.1.3** Wie eine Diagnose identifiziert wird  
  
 Microsoft C erzeugt Fehlermeldungen in der Form:  
  
```  
  
filename( line-number ) : diagnostic Cnumber message  
```  
  
 wobei *filename* der Name der Quelldatei ist, in der der Fehler aufgetreten ist; *line\-number* ist die Nummer der Zeile, in der der Compiler den Fehler festgestellt hat; `diagnostic` ist entweder "error" oder "warning"; `number` ist eine eindeutige vierstellige Zahl \(der ein **C** vorangestellt ist, wie in der Syntax kenntlich gemacht\), die den Fehler bzw. die Warnung angibt; `message` ist eine erläuternde Meldung.  
  
## Siehe auch  
 [Durch die Implementierung definiertes Verhalten](../c-language/implementation-defined-behavior.md)