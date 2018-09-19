---
title: __invlpg | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __invlpg
- __invlpg_cpp
dev_langs:
- C++
helpviewer_keywords:
- invlpg instruction
- __invlpg intrinsic
ms.assetid: 3fb3633f-d9b7-4ec0-9e7f-a7f2fa8ed794
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1ada416217be672da8f93c777b0b2a6e12684711
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45703026"
---
# <a name="invlpg"></a>__invlpg
**Microsoft-spezifisch**  
  
 Generiert die X86 `invlpg` -Anweisung, die die Translation Lookaside Buffer, TLB (TLB) für die Seite mit dem zugeordneten Speicher verweist erklärt `Address`.  
  
## <a name="syntax"></a>Syntax  
  
```  
void __invlpg(  
   void* Address  
);  
```  
  
#### <a name="parameters"></a>Parameter  
*Adresse*<br/>
[in] Eine 64-Bit-Adresse.  
  
## <a name="requirements"></a>Anforderungen  
  
|Systemintern|Architektur|  
|---------------|------------------|  
|`__invlpg`|x86, x64|  
  
 **Headerdatei** \<intrin.h >  
  
## <a name="remarks"></a>Hinweise  
 Die systeminterne Funktion `__invlpg` eine privilegierte Anweisung ausgibt, und ist nur verfügbar im Kernel-Modus mit einer Berechtigungsstufe (CPL) von 0.  
  
 Diese Routine ist nur als systeminterne Funktion verfügbar.  
  
**Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)