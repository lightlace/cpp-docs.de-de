---
title: "Steuerungsflags"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "c.flags"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "Debugheap, Steuerungskennzeichen"
  - "Flags, Steuerelement"
  - "Heapzuordnung, Steuerungskennzeichen"
ms.assetid: 8dbd24a5-0633-42d1-9771-776db338465f
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Steuerungsflags
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Debugversion der C\-Laufzeitbibliothek verwendet Microsoft die folgenden Flags, um den Heapbelegungs\- und Berichterstellungsprozess zu steuern.  Weitere Informationen finden Sie unter [CRT\-Debug\-Techniken](../Topic/CRT%20Debugging%20Techniques.md).  
  
|Flag|**Beschreibung**|  
|----------|----------------------|  
|[\_CRTDBG\_MAP\_ALLOC](../c-runtime-library/crtdbg-map-alloc.md)|Ordnet den Basisheapfunktionen zu ihren Debugversionsentsprechungen zu|  
|[\_DEBUG](../c-runtime-library/debug.md)|Ermöglicht die Verwendung von Debuggingsversionen Laufzeitfunktionen der|  
|[\_crtDbgFlag](../c-runtime-library/crtdbgflag.md)|Steuerelemente, wie der Debugheapmanager Zuordnungen nachverfolgt|  
  
 Diese Flags können mit einer Befehlszeilenoption \/D\- oder Direktive mit `#define` definiert werden.  Wenn das Flag mit `#define` definiert wird, müssen die Direktive werden vor der Headerdateieinschließungsanweisung für die Routinedeklarationen.  
  
## Siehe auch  
 [Globale Variablen und Standardtypen](../c-runtime-library/global-variables-and-standard-types.md)