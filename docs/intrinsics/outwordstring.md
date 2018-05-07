---
title: __outwordstring | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __outwordstring
dev_langs:
- C++
helpviewer_keywords:
- rep outsw instruction
- __outwordstring intrinsic
- outsw instruction
ms.assetid: b470c7a0-1de9-4370-886a-b2c3a1f842f4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fc25fdc4d43b7454761787264583b5e4f8fa47e0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="outwordstring"></a>__outwordstring
**Microsoft-spezifisch**  
  
 Generiert die `rep outsw` -Anweisung, die sendet `Count` beginnenden Wörtern `Buffer` Ausgang von angegebenen e/a- `Port`.  
  
## <a name="syntax"></a>Syntax  
  
```  
void __outwordstring(   
   unsigned short Port,   
   unsigned short* Buffer,   
   unsigned long Count   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 [in] `Port`  
 Der Port, an die die Daten gesendet werden soll.  
  
 [in] `Buffer`  
 Ein Zeiger auf die Daten auf den angegebenen Port gesendet werden.  
  
 [in] `Count`  
 Die Anzahl der Wörter zu senden.  
  
## <a name="requirements"></a>Anforderungen  
  
|Systemintern|Architektur|  
|---------------|------------------|  
|`__outwordstring`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Headerdatei** \<intrin.h >  
  
## <a name="remarks"></a>Hinweise  
 Diese Routine ist nur als systeminterne Funktion verfügbar.  
  
**Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)