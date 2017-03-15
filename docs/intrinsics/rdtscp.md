---
title: "__rdtscp | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "__rdtscp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "rdtscp intrinsic"
  - "__rdtscp intrinsic"
  - "rdtscp-Anweisung"
ms.assetid: f17d9a9c-88bb-44e0-b69d-d516bc1c93ee
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# __rdtscp
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Generiert die `rdtscp`\-Anweisung, schreibt `TSC_AUX[31:0`\] und gibt den 64\-Bit\-Zeitstempelleistungsindikator im Speicher zurück \(`TSC)` Ergebnis.  
  
## Syntax  
  
```  
unsigned __int64 __rdtscp(  
   unsigned int * Aux  
);  
```  
  
#### Parameter  
 \[out\] `Aux`  
 Zeiger auf einen Speicherort, der den Inhalt des Registers besondere MACHINE `TSC_AUX[31:0]`enthält.  
  
## Rückgabewert  
 Eine 64\-Bit\-Ganzzahl ohne Vorzeichen\-Taktanzahl.  
  
## Anforderungen  
  
|Intrinsisch|Architektur|  
|-----------------|-----------------|  
|`__rdtscp`|Familie 0Fh AMDs NPT oder höhere Versionen|  
  
 **Headerdatei** \<intrin.h\>  
  
## Hinweise  
 Das systeminterne generiert die `rdtscp`\-Anweisung.  Um Hardwareunterstützung für diese Anweisung zu bestimmen, `__cpuid`direkt aufrufen und `InfoType=0x80000001` mit Prüfbit 27 von `CPUInfo[3] (EDX)`.  Das Bit beträgt 1, wenn die Anweisung unterstützt wird, andernfalls 0.  Wenn Sie diesen Code ausführen, der Hardware, das auf die ist, die nicht direkt `rdtscp`\-Anweisung unterstützt, die Ergebnisse sind unvorhersehbar.  
  
> [!CAUTION]
>  Im Gegensatz zu `rdtsc`ist eine `rdtscp` serialisierende Anweisung. trotzdem kann der Compiler Code um systeminternes dieses verschieben.  
  
 Die Interpretation des TSC\-Werts in dieser Generation der Hardware unterscheidet sich von dem in früheren Versionen von [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)].  Weitere Informationen finden Sie handbücher Hardware.  
  
 Die Bedeutung des Werts in `TSC_AUX[31:0]` hängt vom Betriebssystem ab.  
  
## Beispiel  
  
```  
#include <intrin.h>   
#include <stdio.h>  
int main()   
{  
 unsigned __int64 i;  
 unsigned int ui;  
 i = __rdtscp(&ui);  
 printf_s("%I64d ticks\n", i);  
 printf_s("TSC_AUX was %x\n", ui);  
}  
```  
  
  **3363423610155519 Teilstrich**  
**TSC\_AUX war 0**   
## BEENDEN Sie Microsoft\-Besonderen  
 Copyright 2007 bis Advanced Micro Devices, Inc.  Alle Rechte vorbehalten.  Reproduziert mit zulässigen Advanced Micro Devices, Inc.  
  
## Siehe auch  
 [\_\_rdtsc](../intrinsics/rdtsc.md)   
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)