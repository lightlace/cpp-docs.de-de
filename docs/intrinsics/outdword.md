---
title: __outdword | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __outdword
dev_langs:
- C++
helpviewer_keywords:
- out instruction
- outdword instruction
- __outdword intrinsic
ms.assetid: ed1e4994-a84b-4759-8bf9-cd48fb073f4d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1181cfa4fc2868fe96deb1d68d4140b9ab80e29b
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45708681"
---
# <a name="outdword"></a>__outdword
**Microsoft-spezifisch**  
  
 Generiert die `out` Anweisung zum Senden einer zeigt Doppelwort `Data` der Port `Port`.  
  
## <a name="syntax"></a>Syntax  
  
```  
void __outdword(   
   unsigned short Port,   
   unsigned long Data   
);  
```  
  
#### <a name="parameters"></a>Parameter  
*Port*<br/>
[in] Der Port, der die Daten zu senden.  
  
*Data*<br/>
[in] Die Doppelwort gesendet werden.  
  
## <a name="requirements"></a>Anforderungen  
  
|Systemintern|Architektur|  
|---------------|------------------|  
|`__outdword`|x86, x64|  
  
 **Headerdatei** \<intrin.h >  
  
## <a name="remarks"></a>Hinweise  
 Diese Routine ist nur als systeminterne Funktion verfügbar.  
  
**Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)