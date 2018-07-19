---
title: _InterlockedCompareExchange128 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- _InterlockedCompareExchange128_cpp
- _InterlockedCompareExchange128
dev_langs:
- C++
helpviewer_keywords:
- cmpxchg16b instruction
- _InterlockedCompareExchange128 intrinsic
ms.assetid: f05918fc-716a-4f6d-b746-1456d6b96c56
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f491f59289a2e3b951e1bad60f260a801ea68bea
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33337934"
---
# <a name="interlockedcompareexchange128"></a>_InterlockedCompareExchange128
**Microsoft-spezifisch**  
  
 Führt einen ineinandergreifenden Vergleich 128-Bit- und Exchange.  
  
## <a name="syntax"></a>Syntax  
  
```  
unsigned char _InterlockedCompareExchange128(  
   __int64 volatile * Destination,  
   __int64 ExchangeHigh,  
   __int64 ExchangeLow,  
   __int64 * ComparandResult  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 [in, out] `Destination`  
 Zeiger auf das Ziel, das ein Array von zwei 64-Bit-Ganzzahlen ist gewissermaßen mit einem 128-Bit-Feld. Die Zieldaten muss 16-Byte-ausgerichtet werden, um eine allgemeine schutzverletzung zu vermeiden.  
  
 [in] `ExchangeHigh`  
 Eine 64-Bit-Ganzzahl, die mit den oberen Teil des Ziels ausgetauscht werden kann.  
  
 [in] `ExchangeLow`  
 Eine 64-Bit-Ganzzahl, die mit des unteren Teils des Zieles ausgetauscht werden kann.  
  
 [in, out] `ComparandResult`  
 Zeiger auf ein Array von zwei 64-Bit-Ganzzahlen (gewissermaßen mit einem 128-Bit-Feld), mit dem Ziel verglichen werden soll.  Bei der Ausgabe ist dieser Wert mit dem ursprünglichen Wert des Ziels überschrieben.  
  
## <a name="return-value"></a>Rückgabewert  
 1, wenn die 128-Bit-comparand-Parameter den ursprünglichen Wert des Ziels entspricht. `ExchangeHigh` und `ExchangeLow` die 128-Bit-Ziel zu überschreiben.  
  
 0, wenn das zu vergleichende Objekt nicht den ursprünglichen Wert des Ziels übereinstimmt. Der Wert des Ziels ist unverändert, und der Wert der comparand-Parameter wird überschrieben, mit dem Wert des Ziels.  
  
## <a name="requirements"></a>Anforderungen  
  
|Systemintern|Architektur|  
|---------------|------------------|  
|`_InterlockedCompareExchange128`|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Headerdatei** \<intrin.h >  
  
## <a name="remarks"></a>Hinweise  
 Diese systeminterne Funktion generiert die `cmpxchg16b` Anweisung (mit der `lock` Präfix) um eine 128-Bit-gesperrten compare_exchange -Operation auszuführen. Diese Anweisung unterstützt frühe Versionen von AMD 64-Bit-Hardware nicht. Prüfen der Hardware-Unterstützung für die `cmpxchg16b` -Anweisung, rufen die `__cpuid` systeminternen Funktionen mit `InfoType=0x00000001 (standard function 1)`. Bit 13 des `CPUInfo[2]` (ECX) ist 1, wenn die Anweisung unterstützt wird.  
  
> [!NOTE]
>  Der Wert des `ComparandResult` wird immer überschrieben. Nach der `lock` -Anweisung dieser systeminternen Funktion sofort kopiert den anfänglichen Wert des `Destination` auf `ComparandResult`. Aus diesem Grund `ComparandResult` und `Destination` sollte zeigen Sie auf unterschiedliche Speicherorte, unerwartetes Verhalten zu vermeiden.  
  
 Sie können zwar `_InterlockedCompareExchange128` für die Low-Level-Threadsynchronisierung, Sie müssen nicht mehr als 128 Bits zu synchronisieren, wenn Sie kleinere Synchronisierungsfunktionen verwenden können (z. B. anderen `_InterlockedCompareExchange` systeminternen Funktionen) stattdessen. Verwendung `_InterlockedCompareExchange128` gegebenenfalls atomaren Zugriff auf einen 128-Bit-Wert im Arbeitsspeicher.  
  
 Wenn Sie Code, verwendet dieser systeminternen Funktion auf Hardware ausgeführt, die nicht unterstützt wird die `cmpxchg16b` -Anweisung, die die Ergebnisse sind unvorhersehbar.  
  
 Diese Routine ist nur als systeminterne Funktion verfügbar.  
  
## <a name="example"></a>Beispiel  
 Dieses Beispiel verwendet `_InterlockedCompareExchange128` hohe Word eines Arrays von zwei 64-Bit-Ganzzahlen mit der Summe der hohen und niedrigen Wörter ersetzen und das niedrige Word zu erhöhen. Der Zugriff auf das Array BigInt.Int ist atomarisch, aber in diesem Beispiel verwendet einen einzelnen Thread und ignoriert das Sperren aus Gründen der Einfachheit.  
  
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
  
```Output  
BigInt.Int[1] = 34, BigInt.Int[0] = 12  
```  
  
**Ende Microsoft-spezifisch**  
 Copyright 2007 erweiterte Micro-Geräte, Inc. Alle Rechte vorbehalten. Reproduziert mit Genehmigung Advanced Micro-Geräte, Inc.  
  
## <a name="see-also"></a>Siehe auch  
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)   
 [Systeminterne Funktionen "_InterlockedCompareExchange"](../intrinsics/interlockedcompareexchange-intrinsic-functions.md)   
 [Konflikt mit dem x86-Compiler](../build/conflicts-with-the-x86-compiler.md)