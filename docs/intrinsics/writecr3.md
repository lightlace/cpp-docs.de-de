---
title: __writecr3 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- _writecr3
dev_langs:
- C++
helpviewer_keywords:
- _writecr3 intrinsic
ms.assetid: 959d49fa-69d5-47cf-88d2-7688367fe38f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 10acb6af23dffef0a7067883ac5dbac5abd9234f
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45724244"
---
# <a name="writecr3"></a>__writecr3
**Microsoft-spezifisch**  
  
 Schreibt den Wert `Data` dem CR3-Register.  
  
## <a name="syntax"></a>Syntax  
  
```  
void writecr3(   
   unsigned __int64 Data   
);  
```  
  
#### <a name="parameters"></a>Parameter  
*Data*<br/>
[in] Der Wert, der registriert wird, CR3 geschrieben werden soll.  
  
## <a name="requirements"></a>Anforderungen  
  
|Systemintern|Architektur|  
|---------------|------------------|  
|`__writecr3`|x86, x64|  
  
 **Headerdatei** \<intrin.h >  
  
## <a name="remarks"></a>Hinweise  
 Diese systeminterne Funktion ist nur im Kernelmodus verfügbar, und die Routine ist nur als systeminterne Funktion verfügbar.  
  
**Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)