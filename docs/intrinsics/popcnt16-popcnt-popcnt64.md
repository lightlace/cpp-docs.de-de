---
title: "__popcnt16, __popcnt, __popcnt64"
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
  - "__popcnt64"
  - "__popcnt"
  - "__popcnt16"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "popcnt-Anweisung"
  - "__popcnt16"
  - "__popcnt64"
  - "__popcnt"
ms.assetid: e525b236-adc8-42df-9b9b-8b7d8c245d3b
caps.latest.revision: 15
caps.handback.revision: "13"
ms.author: "corob"
manager: "ghogen"
---
# __popcnt16, __popcnt, __popcnt64
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Ermittelt die Anzahl von Bits der Leerraum \(eins\) in einer 16 \-, 32 \- oder 64: Byte\-ganzen Zahl ohne Vorzeichen.  
  
## Syntax  
  
```  
unsigned short __popcnt16(  
   unsigned short value  
);  
unsigned int __popcnt(  
   unsigned int value  
);  
unsigned __int64 __popcnt64(  
   unsigned __int64 value  
);  
```  
  
#### Parameter  
 \[in\] `value`  
 Das 16 \-, 32 \- oder zum 64\-Bit\-Ganzzahl ohne Vorzeichen wir die Anzahl der Leerraum.  
  
## Rückgabewert  
 Die Anzahl der Bits im `value`\-Parameter.  
  
## Anforderungen  
  
|Intrinsisch|Architektur|  
|-----------------|-----------------|  
|`__popcnt16`|Erweiterte Bitmanipulation|  
|`__popcnt`|Erweiterte Bitmanipulation|  
|`__popcnt64`|Erweiterte Bitmanipulation im 64\-Bit\-Modus.|  
  
 **Headerdatei** \<intrin.h\>  
  
## Hinweise  
 Jede dieser systeminternen Funktionen generiert die`popcnt`\-Anweisung.  Die Größe des Werts, den die`popcnt`\-Anweisung zurückgibt, entspricht der Größe des Arguments.  In 32\-Bit\- Modus gibt es keine 64\-Bit\- allgemeinen Register, sodass kein 64\-Bit\- `popcnt`.  
  
 Um Hardwareunterstützung für die `popcnt`Anweisung zu bestimmen, `__cpuid` direkt aufrufen und `InfoType=0x00000001` mit Prüfbit 23 von `CPUInfo[2] (ECX)`.  Das Bit beträgt 1, wenn die Anweisung unterstützt wird, andernfalls 0.  Wenn Sie diesen Code ausführen, der Hardware, das auf die ist, die nicht direkt `popcnt`\-Anweisung unterstützt, die Ergebnisse sind unvorhersehbar.  
  
## Beispiel  
  
```  
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
    usr = __popcnt16(us[i]);  
    cout << "__popcnt16(0x" << hex << us[i] << ") = " << dec << usr << endl;  
  }  
  
  for (int i=0; i<4; i++) {  
    uir = __popcnt(ui[i]);  
    cout << "__popcnt(0x" << hex << ui[i] << ") = " << dec << uir << endl;  
  }  
}  
  
```  
  
  **\_\_popcnt16 \(0x0\) \= 0**  
 **\_\_popcnt16 \(0xff\) \= 8**  
 **\_\_popcnt16 \(0xffff\) \= 16**  
 **\_\_popcnt \(0x0\) \= 0**  
 **\_\_popcnt \(0xff\) \= 8**  
 **\_\_oopcnt \(0xffff\) \= 16**  
 **\_\_popcnt \(0xffffffff\) \= 32**   
## Microsoft ENDES bestimmten  
 Copyright 2007 bis Advanced Micro Devices, Inc.  Alle Rechte vorbehalten.  Reproduziert mit zulässigen Advanced Micro Devices, Inc.  
  
## Siehe auch  
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)