---
title: __ll_lshift | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- __ll_lshift_cpp
- __ll_lshift
dev_langs: C++
helpviewer_keywords:
- ll_lshift intrinsic
- __ll_lshift intrinsic
ms.assetid: fe98f733-426d-44b3-8f24-5d0d6d44bd94
caps.latest.revision: "16"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 0d827b375cd382ff4f298f2933fc8a3109d2f846
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="lllshift"></a>__ll_lshift
**Microsoft-spezifisch**  
  
 Verschiebt die angegebenen 64-Bit-Wert durch die angegebene Anzahl von Bits nach links.  
  
## <a name="syntax"></a>Syntax  
  
```  
unsigned __int64 __ll_lshift(  
   unsigned __int64 Mask,  
   int nBit  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 [in] `Mask`  
 Der 64-Bit-Ganzzahl-Wert, nach links verschoben werden soll.  
  
 [in] `nBit`  
 Die Anzahl der zu verschiebenden Bits.  
  
## <a name="return-value"></a>Rückgabewert  
 Die Maske verschoben nach links `nBit` Bits.  
  
## <a name="requirements"></a>Anforderungen  
  
|Systemintern|Architektur|  
|---------------|------------------|  
|`__ll_lshift`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Headerdatei** \<intrin.h >  
  
## <a name="remarks"></a>Hinweise  
 Wenn Sie das Programm die Verwendung der 64-Bit-Architektur kompiliert und `nBit` ist größer als 63, ist die Anzahl der zu verschiebenden Bits `nBit` modulo 64. Wenn Sie das Programm die Verwendung der 32-Bit-Architektur kompiliert und `nBit` ist größer als 31, ist die Anzahl der zu verschiebenden Bits `nBit` modulo 32.  
  
 Die `ll` im Namen gibt an, dass dies eine Operation auf `long long` (`__int64`).  
  
## <a name="example"></a>Beispiel  
  
```  
// ll_lshift.cpp  
// compile with: /EHsc  
// processor: x86, x64  
#include <iostream>  
#include <intrin.h>  
using namespace std;  
  
#pragma intrinsic(__ll_lshift)  
  
int main()  
{  
   unsigned __int64 Mask = 0x100;  
   int nBit = 8;  
   Mask = __ll_lshift(Mask, nBit);  
   cout << hex << Mask << endl;  
}  
```  
  
## <a name="output"></a>Ausgabe  
  
```  
10000  
```  
  
 **Hinweis** keine nicht signierten Version des Vorgangs nach links verschieben vorhanden ist. Grund hierfür ist, `__ll_lshift` bereits ohne Vorzeichen Eingabeparameter verwendet. Im Gegensatz zu den nach rechts verschieben gibt es keine Abhängigkeit Anmeldung für die Verschiebung nach links, da das niederwertigste Bit im Ergebnis immer unabhängig vom Vorzeichen des Werts verschoben, auf NULL festgelegt ist.  
  
**Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [__ll_rshift](../intrinsics/ll-rshift.md)   
 [__ull_rshift](../intrinsics/ull-rshift.md)   
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)