---
title: "Verwenden von Operatoren in __asm-Bl&#246;cken | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__asm-Schlüsselwort [C++], Operatoren"
  - "Klammern [ ]"
  - "Klammern [ ], __asm-Blöcke"
  - "Operatoren [C++], Verwenden in __asm-Blöcken"
  - "Eckige Klammern [ ]"
  - "Eckige Klammern [ ], __asm-Blöcke"
ms.assetid: a26ccfd4-40ae-4a61-952f-c417982aa8dd
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Verwenden von Operatoren in __asm-Bl&#246;cken
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

## Microsoft\-spezifisch  
 Ein Block kann bestimmte Operatoren `__asm` C oder C\+\+, wie der **\<\<**\-Operator nicht verwenden.  Bei Operatoren, die von C und MASM, wie Operator \*, werden als Assemblersprachen Operatoren interpretiert.  Zum Beispiel außerhalb eines `__asm`\-Blocks, werden eckige Klammern \(\[\]\) als Beilegen von Arrayfeldindizes interpretiert, die C automatisch an die Größe eines Elements im Array skaliert.  Innerhalb eines `__asm`\-Blocks werden sie als der Operator MASM\-Index erwähnt, der einen unskalierte Byteoffset von jedem Datenobjekt oder Bezeichnung ergibt \(nicht nur ein Array\).  Der folgende Code veranschaulicht den Unterschied:  
  
```  
int array[10];  
  
__asm mov array[6], bx ;  Store BX at array+6 (not scaled)  
  
array[6] = 0;         /* Store 0 at array+24 (scaled) */  
```  
  
 Der erste Verweis auf `array` wird nicht skaliert, aber der zweiten ist.  Beachten Sie, dass Sie den TYPE\-Operator verwenden können, um die Skalierung auf Grundlage einer Konstante zu erzielen.  Beispielsweise sind die folgenden Anweisungen:  
  
```  
__asm mov array[6 * TYPE int], 0 ; Store 0 at array + 24  
  
array[6] = 0;                   /* Store 0 at array + 24 */  
```  
  
 **Microsoft ENDES bestimmten**  
  
## Siehe auch  
 [Verwenden von C oder C\+\+ in \_\_asm\-Blöcken](../../assembler/inline/using-c-or-cpp-in-asm-blocks.md)