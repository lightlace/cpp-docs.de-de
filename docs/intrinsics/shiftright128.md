---
title: __shiftright128 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __shiftright128
dev_langs:
- C++
helpviewer_keywords:
- __shiftright128 intrinsic
ms.assetid: 5419a6c4-0de1-43fb-b314-4faa5b2d051f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 393138916bf29fd9adb5dceb0b8612b576b84e76
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="shiftright128"></a>__shiftright128
**Microsoft-spezifisch**  
  
 Verschiebt eine 128-Bit-Menge, dargestellt als zwei 64-Bit-Mengen `LowPart` und `HighPart`, um eine angegebene Anzahl von Bits, die durch `Shift` definiert wird, nach rechts und gibt die unteren 64 Bits des Ergebnisses zurück.  
  
## <a name="syntax"></a>Syntax  
  
```  
unsigned __int64 __shiftright128(   
   unsigned __int64 LowPart,   
   unsigned __int64 HighPart,   
   unsigned char Shift   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 [in] `LowPart`  
 Die unteren 64 Bits der zu verschiebenden 128-Bit-Menge.  
  
 [in] `HighPart`  
 Die oberen 64 Bits der zu verschiebenden 128-Bit-Menge.  
  
 [in] `Shift`  
 Die Anzahl der zu verschiebenden Bits.  
  
## <a name="return-value"></a>Rückgabewert  
 Die unteren 64 Bits des Ergebnisses.  
  
## <a name="requirements"></a>Anforderungen  
  
|Systemintern|Architektur|  
|---------------|------------------|  
|`__shiftright128`|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Headerdatei** \<intrin.h >  
  
## <a name="remarks"></a>Hinweise  
 Der `Shift`-Wert ist immer modulo 64. So verschiebt z. B. beim Aufrufen von `__shiftright128(0, 1, 64)` die Funktion die `0`-Bits des oberen Teils nach rechts und gibt einen unteren Teil von `0` und nicht von `1` zurück, wie man annehmen könnte.  
  
## <a name="example"></a>Beispiel  
 Ein Beispiel finden Sie unter [__shiftleft128](../intrinsics/shiftleft128.md).  
  
**Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [__shiftleft128](../intrinsics/shiftleft128.md)   
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)