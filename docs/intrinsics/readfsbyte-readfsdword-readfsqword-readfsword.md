---
title: __readfsbyte, __readfsdword, __readfsqword, __readfsword | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- __readfsword
- __readfsdword
- __readfsbyte
- __readfsqword
dev_langs:
- C++
helpviewer_keywords:
- __readfsword intrinsic
- readfsword intrinsic
- __readfsdword intrinsic
- readfsbyte intrinsic
- __readfsbyte intrinsic
- readfsdword intrinsic
- readfsqword intrinsic
- __readfsqword intrinsic
ms.assetid: f6ee7203-4179-402c-a464-0746c84ce6ac
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8d7430e8ebdf86acb7db2d8605d63c4d94f18dd5
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="readfsbyte-readfsdword-readfsqword-readfsword"></a>__readfsbyte, __readfsdword, __readfsqword, __readfsword
**Microsoft-spezifisch**  
  
 Lesen Sie Arbeitsspeicher von einem Ort, ein Offset relativ zum Anfang des Segments FS angegeben wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
unsigned char __readfsbyte(   
   unsigned long Offset   
);  
unsigned short __readfsword(   
   unsigned long Offset   
);  
unsigned long __readfsdword(   
   unsigned long Offset  
);  
unsigned __int64 __readfsqword(   
   unsigned long Offset   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 [in] `Offset`  
 Der Offset vom Anfang des `FS` zum Auslesen.  
  
## <a name="return-value"></a>Rückgabewert  
 Der Speicherinhalt des Byte, Wort, Doppelwort oder Vierfachwort (wie durch den Namen der aufgerufenen Funktion angegeben wird) an der Position `FS:[Offset]`.  
  
## <a name="requirements"></a>Anforderungen  
  
|Systemintern|Architektur|  
|---------------|------------------|  
|`__readfsbyte`|x86|  
|`__readfsdword`|x86|  
|`__readfsqword`|x86|  
|`__readfsword`|x86|  
  
 **Headerdatei** \<intrin.h >  
  
## <a name="remarks"></a>Hinweise  
 Diese Routinen sind nur als systeminterne Funktionen verfügbar.  
  
**Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [__writefsbyte, \__writefsdword, \__writefsqword, \__writefsword](../intrinsics/writefsbyte-writefsdword-writefsqword-writefsword.md)   
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)