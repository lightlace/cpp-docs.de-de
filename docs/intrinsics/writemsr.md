---
title: __writemsr | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __writemsr
dev_langs:
- C++
helpviewer_keywords:
- Write Model Specific Register instruction
- wrmsr instruction
- __writemsr intrinsic
ms.assetid: 938b1553-51a8-4822-a818-6bed79b0fde5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 627e6bfdb33561e3d4be55aebf07e831b6cdc035
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45705132"
---
# <a name="writemsr"></a>__writemsr
**Microsoft-spezifisch**  
  
 Generiert das Schreiben in Model Specific Register (`wrmsr`) Anweisung.  
  
## <a name="syntax"></a>Syntax  
  
```  
void __writemsr(   
   unsigned long Register,   
   unsigned __int64 Value   
);  
```  
  
#### <a name="parameters"></a>Parameter  
*Registrieren*<br/>
[in] Das Modell bestimmte registrieren.  
  
*Wert*<br/>
[in] Der zu schreibende Wert.  
  
## <a name="requirements"></a>Anforderungen  
  
|Systemintern|Architektur|  
|---------------|------------------|  
|`__writemsr`|x86, x64|  
  
 **Headerdatei** \<intrin.h >  
  
## <a name="remarks"></a>Hinweise  
 Diese Funktion kann nur im Kernel-Modus verwendet werden, und diese Routine ist nur als systeminterne Funktion verfügbar.  
  
**Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)