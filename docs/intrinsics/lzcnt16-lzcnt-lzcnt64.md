---
title: "__lzcnt16, __lzcnt, __lzcnt64"
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
  - "__lzcnt64"
  - "__lzcnt16"
  - "__lzcnt"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__lzcnt intrinsic"
  - "lzcnt-Anweisung"
  - "lzcnt16 intrinsic"
  - "lzcnt intrinsic"
  - "__lzcnt16 intrinsic"
  - "lzcnt64 intrinsic"
  - "__lzcnt64 intrinsic"
ms.assetid: 412113e7-052e-46e5-8bfa-d5ad72abc10e
caps.latest.revision: 14
caps.handback.revision: "10"
ms.author: "corob"
manager: "ghogen"
---
# __lzcnt16, __lzcnt, __lzcnt64
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Ermittelt die Anzahl von führenden Nullen in eine Drehung um 16 Grad, 32 oder 64 Byte\-ganze Zahl.  
  
## Syntax  
  
```  
unsigned short __lzcnt16(  
   unsigned short value  
);  
unsigned int __lzcnt(  
   unsigned int value  
);  
unsigned __int64 __lzcnt64(  
   unsigned __int64 value  
);  
```  
  
#### Parameter  
 \[in\] `value`  
 Das 16 \-, 32 \- oder für führende Nullen zu überprüfende 64\-Bit\-Ganzzahl ohne Vorzeichen.  
  
## Rückgabewert  
 Die Anzahl der Bits der führenden Null in `value`\-Parameter.  Wenn `value` \(null\) ist, ist der Rückgabewert die Größe des Eingabe\- operanden \(16, 32 oder 64\).  Wenn das höchstwertige Byte eines `value` eins ist, ist der Rückgabewert \(null\).  
  
## Anforderungen  
  
|Intrinsisch|Architektur|  
|-----------------|-----------------|  
|`__lzcnt16`|Erweiterte Bitmanipulation|  
|`__lzcnt`|Erweiterte Bitmanipulation|  
|`__lzcnt64`|Erweiterte Bitmanipulation im 64\-Bit\-Modus.|  
  
 **Headerdatei** \<intrin.h\>  
  
## Hinweise  
 Jede dieser systeminternen Funktionen generiert die `lzcnt`\-Anweisung.  Die Größe des Werts, den die`lzcnt`\-Anweisung zurückgibt, entspricht der Größe des Arguments.  In 32\-Bit\- Modus gibt es keine 64\-Bit\- allgemeinen Register, sodass kein 64\-Bit\- `lzcnt`.  
  
 Um Hardwareunterstützung für die`lzcnt`\-Anweisung zu bestimmen `__cpuid` direkt aufrufen und `InfoType=0x80000001` mit Prüfbit 5 von `CPUInfo[2] (ECX)`.  Das Bit beträgt 1, wenn die Anweisung unterstützt wird, andernfalls 0.  Wenn Sie diesen Code ausführen, der Hardware, das auf die ist, die nicht direkt`lzcnt`\-Anweisung unterstützt, die Ergebnisse sind unvorhersehbar.  
  
## Beispiel  
  
```  
// Compile this test with: /EHsc  
#include <iostream>   
#include <intrin.h>   
using namespace std;   
  
int main()   
{  
  unsigned short us[3] = {0, 0xFF, 0xFFFF};  
  unsigned short usr;  
  unsigned int   ui[4] = {0, 0xFF, 0xFFFF, 0xFFFFFFFF};  
  unsigned int   uir;  
  
  for (int i=0; i<3; i++) {  
    usr = __lzcnt16(us[i]);  
    cout << "__lzcnt16(0x" << hex << us[i] << ") = " << dec << usr << endl;  
  }  
  
  for (int i=0; i<4; i++) {  
    uir = __lzcnt(ui[i]);  
    cout << "__lzcnt(0x" << hex << ui[i] << ") = " << dec << uir << endl;  
  }  
}  
  
```  
  
  **\_\_lzcnt16 \(0x0\) \= 16**  
 **\_\_lzcnt16 \(0xff\) \= 8**  
 **\_\_lzcnt16 \(0xffff\) \= 0**  
 **\_\_lzcnt \(0x0\) \= 32**  
 **\_\_lzcnt \(0xff\) \= 24**  
 **\_\_lzcnt \(0xffff\) \= 16**  
 **\_\_lzcnt \(0xffffffff\) \= 0**   
## BEENDEN Sie Microsoft\-Besonderen  
 Copyright 2007 bis Advanced Micro Devices, Inc.  Alle Rechte vorbehalten.  Reproduziert mit zulässigen Advanced Micro Devices, Inc.  
  
## Siehe auch  
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)