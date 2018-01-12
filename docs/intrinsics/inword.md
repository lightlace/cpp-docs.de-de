---
title: __inword | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- __indword_cpp
- __indword
dev_langs: C++
helpviewer_keywords:
- in instruction
- __inword intrinsic
ms.assetid: 5c617edd-6709-40a1-aad2-40d5e39283c6
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 98d05ad6b424d12c911e726f04f0e0971c3df392
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="inword"></a>__inword
**Microsoft-spezifisch**  
  
 Liest Daten aus den angegebenen Port mit der `in` Anweisung.  
  
## <a name="syntax"></a>Syntax  
  
```  
unsigned short __inword(  
   unsigned short Port  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 [in] `Port`  
 Der Port, aus dem gelesen werden soll.  
  
## <a name="return-value"></a>Rückgabewert  
 Das Wort Daten gelesen werden.  
  
## <a name="requirements"></a>Anforderungen  
  
|Systemintern|Architektur|  
|---------------|------------------|  
|`__inword`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Headerdatei** \<intrin.h >  
  
## <a name="remarks"></a>Hinweise  
 Diese Routine ist nur als systeminterne Funktion verfügbar.  
  
**Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)