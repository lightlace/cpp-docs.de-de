---
title: Systeminterne Funktionen "_InterlockedAdd" | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- _InterlockedAdd64_acq_cpp
- _InterlockedAdd64_acq
- _InterlockedAdd_acq
- _InterlockedAdd_nf
- _InterlockedAdd64_rel
- _InterlockedAdd64
- _InterlockedAdd_cpp
- _InterlockedAdd_rel_cpp
- _InterlockedAdd_rel
- _InterlockedAdd64_rel_cpp
- _InterlockedAdd64_cpp
- _InterlockedAdd_acq_cpp
- _InterlockedAdd64_nf
- _InterlockedAdd
dev_langs: C++
helpviewer_keywords:
- _InterlockedAdd_nf intrinsic
- _InterlockedAdd_rel intrinsic
- _InterlockedAdd intrinsic
- _InterlockedAdd64 intrinsic
- _InterlockedAdd64_acq intrinsic
- _InterlockedAdd64_nf intrinsic
- _InterlockedAdd_acq intrinsic
- _InterlockedAdd64_rel intrinsic
ms.assetid: 3d319603-ea9c-4fdd-ae61-e52430ccc3b1
caps.latest.revision: "14"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: f07115db4d627a1116f9eaefd0f1731841be83ab
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="interlockedadd-intrinsic-functions"></a>Intrinsische Funktionen „_InterlockedAdd“
**Microsoft-spezifisch**  
  
 Führen Sie atomarische Addition aus, die sicherstellt, dass der Vorgang erfolgreich abgeschlossen wird, wenn mehrere Threads auf eine freigegebene Variable zugreifen.  
  
## <a name="syntax"></a>Syntax  
  
```  
long _InterlockedAdd(  
   long volatile * Addend,  
   long Value  
);  
long _InterlockedAdd_acq(  
   long volatile * Addend,  
   long Value  
);  
long _InterlockedAdd_nf(  
   long volatile * Addend,  
   long Value  
);  
long _InterlockedAdd_rel(  
   long volatile * Addend,  
   long Value  
);  
__int64 _InterlockedAdd64(  
   __int64 volatile * Addend,  
   __int64 Value  
);  
__int64 _InterlockedAdd64_acq(  
   __int64 volatile * Addend,  
   __int64 Value  
);  
__int64 _InterlockedAdd64_nf (  
   __int64 volatile * Addend,  
   __int64 Value  
);  
__int64 _InterlockedAdd64_rel(  
   __int64 volatile * Addend,  
   __int64 Value  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 [in, out] `Addend`  
 Zeiger auf die hinzuzufügende ganze Zahl; ersetzt durch das Ergebnis der Addition.  
  
 [in] `Value`  
 Der hinzuzufügende Wert.  
  
## <a name="return-value"></a>Rückgabewert  
 Beide Funktionen geben das Ergebnis der Addition zurück.  
  
## <a name="requirements"></a>Anforderungen  
  
|Systemintern|Architektur|  
|---------------|------------------|  
|`_InterlockedAdd`|ARM|  
|`_InterlockedAdd_acq`|ARM|  
|`_InterlockedAdd_nf`|ARM|  
|`_InterlockedAdd_rel`|ARM|  
|`_InterlockedAdd64`|ARM|  
|`_InterlockedAdd64_acq`|ARM|  
|`_InterlockedAdd64_nf`|ARM|  
|`_InterlockedAdd64_rel`|ARM|  
  
 **Headerdatei** \<intrin.h >  
  
## <a name="remarks"></a>Hinweise  
 Die Versionen dieser Funktionen mit den Suffixen `_acq` oder `_rel` führen eine ineinander greifende Addition gemäß der Semantiken zum Abrufen oder Freigeben durch. Mit Semantiken zum Abrufen (Acquire-Semantiken) ist gemeint, dass das Ergebnis des Vorgangs für alle Threads und Prozessoren sichtbar gemacht wird, bevor nachfolgende Speicherlese- und -schreibvorgänge durchgeführt werden. „Acquire“ ist bei der Eingabe eines kritischen Abschnitts nützlich. Mit Semantiken für die Freigabe (Release-Semantiken) ist gemeint, dass alle Speicherlese- und -schreibvorgänge für alle Threads und Prozessoren sichtbar gemacht werden, bevor das Ergebnis des Vorgangs selbst angezeigt wird. „Release“ ist beim Verlassen eines kritischen Abschnitts nützlich. Die systeminternen Funktionen mit einer `_nf`-Suffix ("no fence") fungieren nicht als Speicherbarriere.  
  
 Diese Routinen sind nur als systeminterne Funktionen verfügbar.  
  
## <a name="example"></a>Beispiel  
  
```  
// interlockedadd.cpp  
// Compile with: /Oi /EHsc  
// processor: ARM  
#include <stdio.h>  
#include <intrin.h>  
  
#pragma intrinsic(_InterlockedAdd)  
  
int main()  
{  
        long data1 = 0xFF00FF00;  
        long data2 = 0x00FF0000;  
        long retval;  
        retval = _InterlockedAdd(&data1, data2);  
        printf("0x%x 0x%x 0x%x", data1, data2, retval);  
}  
```  
  
## <a name="output"></a>Ausgabe  
  
```  
0xffffff00 0xff0000 0xffffff00  
```  
  
## <a name="example"></a>Beispiel  
  
```  
// interlockedadd64.cpp  
// compile with: /Oi /EHsc  
// processor: ARM  
#include <iostream>  
#include <intrin.h>  
using namespace std;  
  
#pragma intrinsic(_InterlockedAdd64)  
  
int main()  
{  
        __int64 data1 = 0x0000FF0000000000;  
        __int64 data2 = 0x00FF0000FFFFFFFF;  
        __int64 retval;  
        cout << hex << data1 << " + " << data2 << " = " ;  
        retval = _InterlockedAdd64(&data1, data2);  
        cout << data1 << endl;  
        cout << "Return value: " << retval << endl;  
}  
```  
  
## <a name="output"></a>Ausgabe  
  
```  
ff0000000000 + ff0000ffffffff = ffff00ffffffff  
Return value: ffff00ffffffff  
```  
  
**Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)   
 [Konflikt mit dem x86-Compiler](../build/conflicts-with-the-x86-compiler.md)