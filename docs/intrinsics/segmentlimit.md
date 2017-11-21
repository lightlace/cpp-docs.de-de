---
title: __segmentlimit | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: __segmentlimit
dev_langs: C++
helpviewer_keywords:
- __segmentlimit intrinsic
- lsl instruction
ms.assetid: d0bc3630-90cb-4185-8667-686fd41e23d4
caps.latest.revision: "21"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 4b23b988069064e938db9f9f87921df901effd1f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="segmentlimit"></a>__segmentlimit
**Microsoft-spezifisch**  
  
 Generiert die `lsl` (Auslastungsgrenze Segment)-Anweisung.  
  
## <a name="syntax"></a>Syntax  
  
```  
unsigned long __segmentlimit(   
   unsigned long a   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 [in] `a`  
 Eine Konstante, die Auswahl des Segments angibt.  
  
## <a name="return-value"></a>Rückgabewert  
 Das Segment Limit des Segments auswahlzeigers gemäß `a`, vorausgesetzt, dass die Auswahl auf der aktuellen Berechtigungsebene gültig und sichtbar ist.  
  
## <a name="requirements"></a>Anforderungen  
  
|Systemintern|Architektur|  
|---------------|------------------|  
|`__segmentlimit`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Headerdatei** \<intrin.h >  
  
## <a name="remarks"></a>Hinweise  
 Wenn das Segment Limit kann nicht abgerufen werden, schlägt diese Anweisung fehl. Diese Anweisung löscht die ZF-Flag und der Rückgabewert nicht definiert ist, bei einem Fehler.  
  
 Diese Routine ist nur als systeminterne Funktion verfügbar.  
  
## <a name="example"></a>Beispiel  
  
```  
#include <stdio.h>  
  
#ifdef _M_IX86  
typedef unsigned int READETYPE;  
#else  
typedef unsigned __int64 READETYPE;  
#endif  
  
#define EFLAGS_ZF      0x00000040  
#define KGDT_R3_DATA    0x0020  
#define RPL_MASK        0x3  
  
extern "C"  
{  
unsigned long __segmentlimit (unsigned long);  
READETYPE __readeflags();  
}  
  
#pragma intrinsic(__readeflags)  
#pragma intrinsic(__segmentlimit)  
  
int main(void)  
{  
   const unsigned long initsl = 0xbaadbabe;  
   READETYPE eflags = 0;  
   unsigned long sl = initsl;  
  
   printf("Before: segment limit =0x%x eflags =0x%x\n", sl, eflags);  
   sl = __segmentlimit(KGDT_R3_DATA + RPL_MASK);  
  
   eflags = __readeflags();  
  
   printf("After: segment limit =0x%x eflags =0x%x eflags.zf = %s\n", sl, eflags, (eflags & EFLAGS_ZF) ? "set" : "clear");  
  
   // If ZF is set, the call to lsl succeeded; if ZF is clear, the call failed.  
   printf("%s\n", eflags & EFLAGS_ZF ? "Success!": "Fail!");  
  
   // You can verify the value of sl to make sure that the instruction wrote to it  
   printf("sl was %s\n", (sl == initsl) ? "unchanged" : "changed");  
  
   return 0;  
}  
```  
  
```Output  
Before: segment limit =0xbaadbabe eflags =0x0  
After: segment limit =0xffffffff eflags =0x256 eflags.zf = set  
Success!  
sl was changed  
```  
  
**Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)