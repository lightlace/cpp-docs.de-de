---
title: "/LINKERMEMBER | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/linkermember"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/LINKERMEMBER (dumpbin-Option)"
  - "LINKERMEMBER (dumpbin-Option)"
  - "-LINKERMEMBER (dumpbin-Option)"
ms.assetid: c96868c1-d70e-4651-ae36-c55b58b16406
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# /LINKERMEMBER
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/LINKERMEMBER[:{1|2}]  
```  
  
## Hinweise  
 Durch diese Option werden die in einer Bibliothek definierten, öffentlichen Symbole angezeigt.  Legen Sie das Argument **1** fest, um Symbole zusammen mit ihrem Offset in Objektreihenfolge anzuzeigen.  Das Argument **2** wird verwendet, wenn Sie Offsets und Indexzahlen von Objekten anzeigen und die Symbole dann zusammen mit dem jeweiligen Objektindex in alphabetischer Reihenfolge anzeigen möchten.  Um beide Ausgaben zu erhalten, geben Sie **\/LINKERMEMBER** ohne Zahlenargument an.  
  
 Für Dateien, die mit der [\/GL](../../build/reference/gl-whole-program-optimization.md)\-Compileroption erstellt wurden, kann nur die DUMPBIN\-Option [\/HEADERS](../../build/reference/headers.md) verwendet werden.  
  
## Siehe auch  
 [DUMPBIN\-Optionen](../../build/reference/dumpbin-options.md)