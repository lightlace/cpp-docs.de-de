---
title: "/IMPORTS (DUMPBIN) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/imports"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/IMPORTS (dumpbin-Option)"
  - "IMPORTS (dumpbin-Option)"
  - "-IMPORTS (dumpbin-Option)"
ms.assetid: 6a296216-2b1b-40f8-8736-cd4553a22456
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# /IMPORTS (DUMPBIN)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/IMPORTS[:file]  
```  
  
 Durch diese Option wird eine Liste \(sowohl statisch verknüpfter als auch [verzögert geladener](../../build/reference/linker-support-for-delay-loaded-dlls.md)\) DLLs, die in eine ausführbare Datei oder DLL importiert werden, sowie alle einzelnen Importe aus jeder dieser DLLs angezeigt.  
  
 Über die optionale Angabe von `file` können Sie festlegen, dass nur die Importe dieser betreffenden DLL angezeigt werden.  Beispiel:  
  
```  
dumpbin /IMPORTS:msvcrt.dll  
```  
  
## Hinweise  
 Die durch diese Option angezeigte Ausgabe ist vergleichbar mit der [\/EXPORTS](../../build/reference/dash-exports.md)\-Ausgabe.  
  
 Für Dateien, die mit der [\/GL](../../build/reference/gl-whole-program-optimization.md)\-Compileroption erstellt wurden, kann nur die DUMPBIN\-Option [\/HEADERS](../../build/reference/headers.md) verwendet werden.  
  
## Siehe auch  
 [DUMPBIN\-Optionen](../../build/reference/dumpbin-options.md)