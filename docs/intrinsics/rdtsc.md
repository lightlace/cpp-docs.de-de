---
title: __rdtsc | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: __rdtsc
dev_langs: C++
helpviewer_keywords:
- __rdtsc intrinsic
- rdtsc instruction
- Read Time Stamp Counter instruction
ms.assetid: e31d0e51-c9bb-42ca-bbe9-a81ffe662387
caps.latest.revision: "17"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: bd108c36dc60f6186d247cd3cf61d27d1dad3239
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="rdtsc"></a>__rdtsc
**Microsoft-spezifisch**  
  
 Generiert die `rdtsc` -Anweisung, die den Prozessor Zeitstempel zurückgegeben. Der Zeitstempel für den Prozessor zeichnet die Anzahl der seit dem letzten Rücksetzen Taktzyklen.  
  
## <a name="syntax"></a>Syntax  
  
```  
unsigned __int64 __rdtsc();  
```  
  
## <a name="return-value"></a>Rückgabewert  
 Eine 64-Bit-Ganzzahl ohne Vorzeichen, die eine Taktanzahl darstellt.  
  
## <a name="requirements"></a>Anforderungen  
  
|Systemintern|Architektur|  
|---------------|------------------|  
|`__rdtsc`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Headerdatei** \<intrin.h >  
  
## <a name="remarks"></a>Hinweise  
 Diese Routine ist nur als systeminterne Funktion verfügbar.  
  
 Die Interpretation des TSC Werts in dieser Generation Hardware unterscheidet sich von dem in früheren Versionen von [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]. Finden Sie unter Hardware-Handbücher für Weitere Informationen.  
  
## <a name="example"></a>Beispiel  
  
```  
// rdtsc.cpp  
// processor: x86, x64  
#include <stdio.h>  
#include <intrin.h>  
  
#pragma intrinsic(__rdtsc)  
  
int main()  
{  
    unsigned __int64 i;  
    i = __rdtsc();  
    printf_s("%I64d ticks\n", i);  
}  
```  
  
```Output  
3363423610155519 ticks  
```  
  
**Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)