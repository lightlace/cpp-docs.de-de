---
title: __rdtscp | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: __rdtscp
dev_langs: C++
helpviewer_keywords:
- rdtscp intrinsic
- __rdtscp intrinsic
- rdtscp instruction
ms.assetid: f17d9a9c-88bb-44e0-b69d-d516bc1c93ee
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 972c789e17b2b42e0df7229b94b4f10aaa5ff470
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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
 [out] `Aux`  
 Zeiger auf einen Speicherort, der den Inhalt des Registers computerspezifische enthält `TSC_AUX[31:0]`.  
  
## <a name="return-value"></a>Rückgabewert  
 Eine 64-Bit-Ganzzahl ohne Vorzeichen Taktanzahl.  
  
## <a name="requirements"></a>Anforderungen  
  
|Systemintern|Architektur|  
|---------------|------------------|  
|`__rdtscp`|AMD NPT Familie 0Fh oder höhere Versionen|  
  
 **Headerdatei** \<intrin.h >  
  
## <a name="remarks"></a>Hinweise  
 Diese systeminterne Funktion generiert die `rdtscp` Anweisung. Um Hardware-Unterstützung für diese Anweisung zu bestimmen, rufen die `__cpuid` systeminternen Funktionen mit `InfoType=0x80000001` und überprüfen Sie Bit 27 von `CPUInfo[3] (EDX)`. Dieses Bit ist 1, wenn die Anweisung unterstützt wird und 0 andernfalls.  Wenn Sie Code, verwendet dieser systeminternen Funktion auf Hardware ausgeführt, die nicht unterstützt wird die `rdtscp` -Anweisung, die die Ergebnisse sind unvorhersehbar.  
  
> [!CAUTION]
>  Im Gegensatz zu `rdtsc`, `rdtscp` ist eine Serialisierung Anweisung; trotzdem kann der Compiler Code umgehen dieses verschieben systeminterne.  
  
 Die Interpretation des TSC Werts in dieser Generation Hardware unterscheidet sich von dem in früheren Versionen von [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)].  Finden Sie unter Hardware-Handbücher für Weitere Informationen.  
  
 Die Bedeutung des Werts in `TSC_AUX[31:0]` richtet sich nach dem Betriebssystem.  
  
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
 Copyright 2007 erweiterte Micro-Geräte, Inc. Alle Rechte vorbehalten. Reproduziert mit Genehmigung Advanced Micro-Geräte, Inc.  
  
## <a name="see-also"></a>Siehe auch  
 [__rdtsc](../intrinsics/rdtsc.md)   
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)