---
title: __writedr | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __writedr
dev_langs:
- C++
helpviewer_keywords:
- __writedr intrinsic
ms.assetid: ac55c1ee-df2f-41d4-a429-6f369d2a934d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b559edf26c847404d718440e86037cab4026297b
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45704950"
---
# <a name="writedr"></a>__writedr
Schreibt den angegebenen Wert dem angegebenen Debug-Register.  
  
## <a name="syntax"></a>Syntax  
  
```  
void __writedr(unsigned DebugRegister, unsigned DebugValue);  
void __writedr(unsigned DebugRegister, unsigned __int64 DebugValue);  
```  
  
#### <a name="parameters"></a>Parameter  
*DebugRegister*<br/>
[in] Registrieren Sie eine Zahl von 0 bis 7, die das Debuggen identifiziert.  
  
*DebugValue*<br/>
[in] Ein Wert zum Schreiben in das Debuggen registrieren.  
  
## <a name="remarks"></a>Hinweise  
 Diese systeminternen Funktionen sind nur im Kernelmodus verfügbar, und die Routinen sind nur als systeminterne Funktionen verfügbar.  
  
## <a name="requirements"></a>Anforderungen  
  
|Systemintern|Architektur|  
|---------------|------------------|  
|`__writedr`|x86, x64|  
  
 **Headerdatei** \<intrin.h >  
  
**Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)   
 [__readdr](../intrinsics/readdr.md)