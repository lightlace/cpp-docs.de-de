---
title: __readcr2 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: __readcr2
dev_langs: C++
helpviewer_keywords: __readcr2 intrinsic
ms.assetid: d02c97d8-1953-46e7-a79e-a781e2c5bf27
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 3018a179bc240f54152b5e62c14035ceea64e222
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="readcr2"></a>__readcr2
**Microsoft-spezifisch**  
  
 Liest das CR2-Register und den Wert zurückgibt.  
  
## <a name="syntax"></a>Syntax  
  
```  
unsigned __int64 __readcr2(void);  
```  
  
## <a name="return-value"></a>Rückgabewert  
 Der Wert im CR2 registrieren.  
  
## <a name="requirements"></a>Anforderungen  
  
|Systemintern|Architektur|  
|---------------|------------------|  
|`__readcr2`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Headerdatei** \<intrin.h >  
  
## <a name="remarks"></a>Hinweise  
 Diese systeminterne Funktion ist nur im Kernelmodus verfügbar, und die Routine ist nur als systeminterne Funktion verfügbar.  
  
**Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)