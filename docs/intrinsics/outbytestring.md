---
title: __outbytestring | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __outbytestring
dev_langs:
- C++
helpviewer_keywords:
- rep outsb instruction
- __outbytestring intrinsic
- outsb instruction
ms.assetid: c9150661-9c18-427f-bae8-710bba6ed78c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 55dc6492faea101df40c2901ced24321822f36e8
ms.sourcegitcommit: a41c4d096afca1e9b619bbbce045b77135d32ae2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2018
ms.locfileid: "42540630"
---
# <a name="outbytestring"></a>__outbytestring
**Microsoft-spezifisch**  
  
 Generiert die `rep outsb` -Anweisung, die die erste sendet `Count` Datenbytes verweist `Buffer` an den Port, der anhand des `Port`.  
  
## <a name="syntax"></a>Syntax  
  
```  
void __outbytestring(   
   unsigned short Port,   
   unsigned char* Buffer,   
   unsigned long Count   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 [in] `Port`  
 Der Port, der die Daten zu senden.  
  
 [in] `Buffer`  
 Die Daten, die über den angegebenen Port gesendet werden.  
  
 [in] `Count`  
 Die Anzahl der Bytes an Daten gesendet werden.  
  
## <a name="requirements"></a>Anforderungen  
  
|Systemintern|Architektur|  
|---------------|------------------|  
|`__outbytestring`|x86, x64|  
  
 **Headerdatei** \<intrin.h >  
  
## <a name="remarks"></a>Hinweise  
 Diese Routine ist nur als systeminterne Funktion verfügbar.  
  
**Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)