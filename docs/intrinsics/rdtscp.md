---
title: "\"__rdtscp\" | Microsoft-Dokumentation"
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __rdtscp
dev_langs:
- C++
helpviewer_keywords:
- rdtscp intrinsic
- __rdtscp intrinsic
- rdtscp instruction
ms.assetid: f17d9a9c-88bb-44e0-b69d-d516bc1c93ee
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3702dcafbc93e34852d5d8fd4a0f1d3c222ea1a6
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45706952"
---
# <a name="rdtscp"></a>__rdtscp

**Microsoft-spezifisch**  
  
 Generiert die `rdtscp` -Anweisung, schreibt `TSC_AUX[31:0`], Arbeitsspeicher und gibt die 64-Bit-Time Stamp Counter (`TSC)` Ergebnis.  
  
## <a name="syntax"></a>Syntax  
  
```  
unsigned __int64 __rdtscp(  
   unsigned int * Aux  
);  
```  
  
#### <a name="parameters"></a>Parameter  
*AUX*<br/>
[out] Zeiger auf einen Speicherort, der den Inhalt des Registers computerspezifische enthält `TSC_AUX[31:0]`.  
  
## <a name="return-value"></a>Rückgabewert  
 Eine 64-Bit-Ganzzahl ohne Vorzeichen-Taktanzahl.  
  
## <a name="requirements"></a>Anforderungen  
  
|Systemintern|Architektur|  
|---------------|------------------|  
|`__rdtscp`|AMD NPT Familie 0Fh oder höhere Versionen|  
  
 **Headerdatei** \<intrin.h >  
  
## <a name="remarks"></a>Hinweise  
 Dieser systeminternen Funktion generiert die `rdtscp` Anweisung. Um hardwareunterstützung für diese Anweisung zu bestimmen, rufen die `__cpuid` systeminternen Funktionen mit `InfoType=0x80000001` und überprüfen Sie wenig 27 `CPUInfo[3] (EDX)`. Dieses Bit ist 1, wenn die Anweisung unterstützt wird, und andernfalls 0.  Wenn Sie Code, verwendet dieser systeminternen Funktion auf Hardware ausgeführt, die nicht unterstützt. die `rdtscp` -Anweisung, die die Ergebnisse sind unvorhersehbar.  
  
> [!CAUTION]
>  Im Gegensatz zu `rdtsc`, `rdtscp` ist eine Serialisierungs-Anweisung; dennoch kann der Compiler Code Umgehung dieses Problems verschieben systeminterne.  
  
 Die Interpretation des TSC-Werts in dieser Generation von Hardware unterscheidet sich von dem in früheren Versionen von X64.  Finden Sie die Hardware-Handbücher für Weitere Informationen.  
  
 Die Bedeutung des Werts in `TSC_AUX[31:0]` auf dem Betriebssystem abhängt.  
  
## <a name="example"></a>Beispiel  
  
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
  
```Output  
3363423610155519 ticks  
TSC_AUX was 0  
```  
  
**Ende Microsoft-spezifisch**  

Copyright 2007 erweiterten Micro-Geräte, Inc. Alle Rechte vorbehalten. Reproduziert werden, mit der Berechtigung, die von erweiterten Micro-Geräte, Inc.  
  
## <a name="see-also"></a>Siehe auch  
 [__rdtsc](../intrinsics/rdtsc.md)   
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)