---
title: "_InterlockedCompareExchange128 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_InterlockedCompareExchange128_cpp"
  - "_InterlockedCompareExchange128"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "cmpxchg16b-Anweisung"
  - "_InterlockedCompareExchange128 intrinsic"
ms.assetid: f05918fc-716a-4f6d-b746-1456d6b96c56
caps.latest.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 15
---
# _InterlockedCompareExchange128
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Führt ein ineinandergegriffenes 128\-Bit vergleichen und austauschen.  
  
## Syntax  
  
```  
unsigned char _InterlockedCompareExchange128(  
   __int64 volatile * Destination,  
   __int64 ExchangeHigh,  
   __int64 ExchangeLow,  
   __int64 * ComparandResult  
);  
```  
  
#### Parameter  
 \[in, out\]  `Destination`  
 Zeiger auf das Ziel, das ein Array von zwei 64\-Bit\-Ganzzahlen ist, die ein 128\-Bit\-Feld angesehen werden.  Die Daten müssen das Ziel 16\-Byte ausgerichtet werden, um eine allgemeine Schutzverletzung zu vermeiden.  
  
 \[in\] `ExchangeHigh`  
 Eine 64\-Bit\-Ganzzahl, die mit dem hohen Teil des Ziels ausgetauscht werden.  
  
 \[in\] `ExchangeLow`  
 Eine 64\-Bit\-Ganzzahl, die mit dem Basis\- Teil des Ziels ausgetauscht werden.  
  
 \[in, out\]  `ComparandResult`  
 Zeiger auf ein Array von zwei zu vergleichenden 64\-Bit\-Ganzzahlen mit dem Ziel betrachtet \(als 128\-Bit\-Feld\).  Das Ergebnis ist dies mit dem ursprünglichen Wert des Ziels überschrieben.  
  
## Rückgabewert  
 1, wenn der 128\-Bit Comparand den ursprünglichen Wert des Ziels entspricht.  `ExchangeHigh``ExchangeLow` und überschreiben die 128\-Bit\-Ziel.  
  
 0, wenn der Comparand nicht zum ursprünglichen Wert des Ziels entspricht.  Der Wert des Ziels bleibt unverändert, und der Wert des Comparand wird mit dem Wert des Ziels überschrieben.  
  
## Anforderungen  
  
|Intrinsisch|Architektur|  
|-----------------|-----------------|  
|`_InterlockedCompareExchange128`|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Headerdatei** \<intrin.h\>  
  
## Hinweise  
 Das systeminterne generiert die`cmpxchg16b`\-Anweisung \(mit dem Präfix\) `lock` ein gesperrtes 128\-Bit auszuführen vergleichen und austauschen.  Frühere Versionen von AMD\-64\-Bit\-Hardware diese Anweisung nicht unterstützt.  Um für Hardwareunterstützung für die `cmpxchg16b`Anweisung zu überprüfen, `__cpuid` direkt mit `InfoType=0x00000001 (standard function 1)`aufrufen.  Bit 13 von `CPUInfo[2]`\(ECX\) beträgt 1, wenn die Anweisung unterstützt wird.  
  
> [!NOTE]
>  Der Wert von `ComparandResult` wird immer außer Kraft.  Nach der `lock`\-Anweisung sofort systeminterne dieses kopiert den Anfangswert von `Destination` zu `ComparandResult`.  Aus diesem Grund sollten `ComparandResult` und `Destination` zeigen, um Speicheradressen zu trennen, um ein unerwartetes Verhalten zu vermeiden.  
  
 Obwohl Sie `_InterlockedCompareExchange128` für die Threadsynchronisierung verwenden können, ist es nicht erforderlich, um über 128 Bits zu synchronisieren, wenn Sie können stattdessen Synchronisierung kleinere Funktionen \(wie die anderen `_InterlockedCompareExchange` systeminternen Funktionen\).  Verwenden Sie `_InterlockedCompareExchange128` , wenn Sie atomaren Zugriff auf einem 128\-Bit\-Wert im Arbeitsspeicher soll.  
  
 Wenn Sie diesen Code ausführen, der Hardware, das auf die ist, die nicht direkt `cmpxchg16b`\-Anweisung unterstützt, die Ergebnisse sind unvorhersehbar.  
  
 Diese Routine ist nur als systeminterne Funktion zur Verfügung.  
  
## Beispiel  
 In diesem Beispiel wird `_InterlockedCompareExchange128` , um das hohe WORD eines Arrays von zwei 64\-Bit\-Ganzzahlen durch die Summe der hohen und niedrigen Wörter zu ersetzen und das niedrige WORD zu erhöhen.  Der Zugriff auf den BigInt.Int\-Array atomar, ist aber dieses Beispiel verwendet einen einzelnen Thread und ignoriert der Einfachheit halber sperren.  
  
```  
// cmpxchg16b.c  
// processor: x64  
// compile with: /EHsc /O2  
#include <stdio.h>  
#include <intrin.h>  
  
typedef struct _LARGE_INTEGER_128 {  
    __int64 Int[2];  
} LARGE_INTEGER_128, *PLARGE_INTEGER_128;  
  
volatile LARGE_INTEGER_128 BigInt;  
  
// This AtomicOp() function atomically performs:  
//   BigInt.Int[1] += BigInt.Int[0]  
//   BigInt.Int[0] += 1  
void AtomicOp ()  
{  
    LARGE_INTEGER_128 Comparand;  
    Comparand.Int[0] = BigInt.Int[0];  
    Comparand.Int[1] = BigInt.Int[1];  
    do {  
        ; // nothing  
    } while (_InterlockedCompareExchange128(BigInt.Int,  
                                            Comparand.Int[0] + Comparand.Int[1],  
                                            Comparand.Int[0] + 1,  
                                            Comparand.Int) == 0);  
}  
  
// In a real application, several threads contend for the value  
// of BigInt.  
// Here we focus on the compare and exchange for simplicity.  
int main(void)  
{  
   BigInt.Int[1] = 23;  
   BigInt.Int[0] = 11;  
   AtomicOp();  
   printf("BigInt.Int[1] = %d, BigInt.Int[0] = %d\n",  
      BigInt.Int[1],BigInt.Int[0]);  
}  
```  
  
  **BigInt.Int \[1\] \= 34, BigInt.Int \[0\] \= 12**   
## Microsoft ENDES bestimmten  
 Copyright 2007 bis Advanced Micro Devices, Inc.  Alle Rechte vorbehalten.  Reproduziert mit zulässigen Advanced Micro Devices, Inc.  
  
## Siehe auch  
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)   
 [\_InterlockedCompareExchange Intrinsic Functions](../intrinsics/interlockedcompareexchange-intrinsic-functions.md)   
 [Konflikt mit dem x86\-Compiler](../build/conflicts-with-the-x86-compiler.md)