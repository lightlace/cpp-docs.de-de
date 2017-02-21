---
title: "__ll_lshift | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "__ll_lshift_cpp"
  - "__ll_lshift"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ll_lshift intrinsic"
  - "__ll_lshift intrinsic"
ms.assetid: fe98f733-426d-44b3-8f24-5d0d6d44bd94
caps.latest.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 16
---
# __ll_lshift
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Verschiebt den angegebenen 64\-Bit\-Wert nach links um die angegebene Anzahl von Bits.  
  
## Syntax  
  
```  
unsigned __int64 __ll_lshift(  
   unsigned __int64 Mask,  
   int nBit  
);  
```  
  
#### Parameter  
 \[in\] `Mask`  
 Der 64\-Bit\-Ganzzahlwert, um links verschoben werden soll.  
  
 \[in\] `nBit`  
 Die Anzahl der Bits verschoben werden soll.  
  
## Rückgabewert  
 Die Maske erfolgt durch `nBit` Bits verschoben.  
  
## Anforderungen  
  
|Intrinsisch|Architektur|  
|-----------------|-----------------|  
|`__ll_lshift`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Headerdatei** \<intrin.h\>  
  
## Hinweise  
 Wenn Sie das Programm mithilfe der Architektur mit 64 Bits kompilieren und `nBit` größer als 63 ist, ist die Anzahl der Bits verschoben werden soll `nBit` sich Modulo 64.  Wenn Sie das Programm mithilfe der Architektur mit 32 Bits kompilieren und `nBit` größer als 31 ist, ist die Anzahl der Bits verschoben werden soll `nBit` sich Modulo 32.  
  
 `ll` im Titel gibt an, dass dies ein Vorgang für `long long` \(`__int64`\) ist.  
  
## Beispiel  
  
```  
// ll_lshift.cpp  
// compile with: /EHsc  
// processor: x86, x64  
#include <iostream>  
#include <intrin.h>  
using namespace std;  
  
#pragma intrinsic(__ll_lshift)  
  
int main()  
{  
   unsigned __int64 Mask = 0x100;  
   int nBit = 8;  
   Mask = __ll_lshift(Mask, nBit);  
   cout << hex << Mask << endl;  
}  
```  
  
## Output  
  
```  
10000  
```  
  
 **Hinweis** Es gibt keine Version ohne Vorzeichen der Linksschiebeoperation.  Dies liegt daran, dass `__ll_lshift` bereits einen Eingabeparameter ohne Vorzeichen verwendet.  Im Gegensatz zum Verschiebung nach rechts gibt es keine Zeichen abhängigkeit für die Verschiebung nach links, da das niedrigstwertige Byte im Ergebnis immer auf Null unabhängig davon, welche Zeichen des verschobenen Werts gestellt wird.  
  
### Microsoft ENDES bestimmten  
  
## Siehe auch  
 [\_\_ll\_rshift](../intrinsics/ll-rshift.md)   
 [\_\_ull\_rshift](../intrinsics/ull-rshift.md)   
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)