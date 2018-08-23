---
title: __ll_lshift | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __ll_lshift_cpp
- __ll_lshift
dev_langs:
- C++
helpviewer_keywords:
- ll_lshift intrinsic
- __ll_lshift intrinsic
ms.assetid: fe98f733-426d-44b3-8f24-5d0d6d44bd94
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 364ad39bfe47ff04c4a1eefb52b32ed4bddb7809
ms.sourcegitcommit: a41c4d096afca1e9b619bbbce045b77135d32ae2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2018
ms.locfileid: "42541047"
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
 Der 64-Bit-Ganzzahl-Wert, um nach links verschoben werden soll.  
  
 [in] `nBit`  
 Die Anzahl der zu verschiebenden Bits.  
  
## <a name="return-value"></a>Rückgabewert  
 Die Maske verschoben nach links durch `nBit` Bits.  
  
## <a name="requirements"></a>Anforderungen  
  
|Systemintern|Architektur|  
|---------------|------------------|  
|`__ll_lshift`|x86, x64|  
  
 **Headerdatei** \<intrin.h >  
  
## <a name="remarks"></a>Hinweise  
 Wenn Sie das Programm mithilfe der 64-Bit-Architektur kompilieren und `nBit` ist größer als 63, ist die Anzahl der zu verschiebenden Bits `nBit` modulo-64. Wenn Sie das Programm, das die 32-Bit-Architektur kompilieren und `nBit` ist größer als 31, die Anzahl der zu verschiebenden Bits wird `nBit` modulo 32.  
  
 Die `ll` im Namen gibt an, dass dieser eine Operation auf `long long` (`__int64`).  
  
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
  
 **Beachten Sie** keine nicht signierten Version des Vorgangs nach links verschieben vorhanden ist. Grund hierfür ist, `__ll_lshift` bereits ohne Vorzeichen Eingabeparameter verwendet. Im Gegensatz zu den nach rechts verschieben besteht es keine Abhängigkeit Anmeldung für die Verschiebung nach links, da das niederwertigste Bit im Ergebnis immer auf NULL, unabhängig vom Vorzeichen des Werts verschoben festgelegt ist.  
  
**Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [__ll_rshift](../intrinsics/ll-rshift.md)   
 [__ull_rshift](../intrinsics/ull-rshift.md)   
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)