---
title: __readcr3 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: __readcr3
dev_langs: C++
helpviewer_keywords: __readcr3 intrinsic
ms.assetid: e24392c3-cad7-4788-8f31-94bf2e9e0053
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: a4769a6391724e8881182b1c9a78191a2f0ca089
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="readcr3"></a>__readcr3
**Microsoft-spezifisch**  
  
 Liest das CR3-Register und den Wert zurückgibt.  
  
## <a name="syntax"></a>Syntax  
  
```  
unsigned __int64 __readcr3(void);  
```  
  
## <a name="return-value"></a>Rückgabewert  
 Der Wert im CR3 registrieren.  
  
## <a name="requirements"></a>Anforderungen  
  
|Systemintern|Architektur|  
|---------------|------------------|  
|`__readcr3`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Headerdatei** \<intrin.h >  
  
## <a name="remarks"></a>Hinweise  
 Diese systeminterne Funktion ist nur im Kernelmodus verfügbar, und die Routine ist nur als systeminterne Funktion verfügbar.  
  
**Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)