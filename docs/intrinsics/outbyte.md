---
title: __outbyte | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __outbyte
dev_langs:
- C++
helpviewer_keywords:
- out instruction
- __outbyte intrinsic
ms.assetid: c4cd1a34-8a02-4e37-993d-3201bc17901a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cff8c2e8abfff713b4044ce58104c58b0a96da12
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45719265"
---
# <a name="outbyte"></a>__outbyte
**Microsoft-spezifisch**  
  
 Generiert die `out` -Anweisung, die mit 1 Byte gemäß sendet `Data` der e/a-Port anhand des `Port`.  
  
## <a name="syntax"></a>Syntax  
  
```  
void __outbyte(   
   unsigned short Port,   
   unsigned char Data   
);  
```  
  
#### <a name="parameters"></a>Parameter  
*Port*<br/>
[in] Der Port, der die Daten zu senden.  
  
*Data*<br/>
[in] Das Byte, die über den angegebenen Port gesendet werden.  
  
## <a name="requirements"></a>Anforderungen  
  
|Systemintern|Architektur|  
|---------------|------------------|  
|`__outbyte`|x86, x64|  
  
 **Headerdatei** \<intrin.h >  
  
## <a name="remarks"></a>Hinweise  
 Diese Routine ist nur als systeminterne Funktion verfügbar.  
  
**Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)