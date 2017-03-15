---
title: "__shiftright128 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "__shiftright128"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__shiftright128 intrinsic"
ms.assetid: 5419a6c4-0de1-43fb-b314-4faa5b2d051f
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# __shiftright128
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Verschiebt eine 128\-Bit\-Menge, dargestellt als zwei 64\-Bit\-Mengen `LowPart` und `HighPart`, um eine angegebene Anzahl von Bits, die durch `Shift` definiert wird, nach rechts und gibt die unteren 64 Bits des Ergebnisses zurück.  
  
## Syntax  
  
```  
unsigned __int64 __shiftright128(     unsigned __int64 LowPart,     unsigned __int64 HighPart,     unsigned char Shift  );  
```  
  
#### Parameter  
 \[in\] `LowPart`  
 Die unteren 64 Bits der zu verschiebenden 128\-Bit\-Menge.  
  
 \[in\] `HighPart`  
 Die oberen 64 Bits der zu verschiebenden 128\-Bit\-Menge.  
  
 \[in\] `Shift`  
 Die Anzahl der zu verschiebenden Bits.  
  
## Rückgabewert  
 Die unteren 64 Bits des Ergebnisses.  
  
## Anforderungen  
  
|Systemintern|Architektur|  
|------------------|-----------------|  
|`__shiftright128`|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Headerdatei** \<intrin.h\>  
  
## Hinweise  
 Der `Shift`\-Wert ist immer modulo 64. So verschiebt z. B. beim Aufrufen von `__shiftright128(0, 1, 64)` die Funktion die `0`\-Bits des oberen Teils nach rechts und gibt einen unteren Teil von `0` und nicht von `1` zurück, wie man annehmen könnte.  
  
## Beispiel  
 Ein Beispiel finden Sie unter [\_\_shiftleft128](../intrinsics/shiftleft128.md).  
  
## Ende Microsoft\-spezifisch  
  
## Siehe auch  
 [\_\_shiftleft128](../intrinsics/shiftleft128.md)   
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)