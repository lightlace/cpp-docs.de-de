---
title: __readpmc | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: __readpmc
dev_langs: C++
helpviewer_keywords:
- Read Performance Monitoring Counters instruction
- __readpmc intrinsic
- rdpmc instruction
ms.assetid: 14ed45a6-28b6-4635-8437-a597c04b43d4
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 323ad8624db725a779110c89f1e8972f74da5060
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="readpmc"></a>__readpmc
**Microsoft-spezifisch**  
  
 Generiert die `rdpmc` -Anweisung, die den vom angegebenen Leistungsindikator liest `counter`.  
  
## <a name="syntax"></a>Syntax  
  
```  
unsigned __int64 __readpmc(   
   unsigned long counter   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 [in] `counter`  
 Der Leistungsindikator, zu lesen.  
  
## <a name="return-value"></a>Rückgabewert  
 Der Wert des angegebenen Leistungsindikators.  
  
## <a name="requirements"></a>Anforderungen  
  
|Systemintern|Architektur|  
|---------------|------------------|  
|`__readpmc`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Headerdatei** \<intrin.h >  
  
## <a name="remarks"></a>Hinweise  
 Diese systeminterne Funktion nur im Kernelmodus verfügbar ist, und die Routine ist nur als systeminterne Funktion verfügbar.  
  
**Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)