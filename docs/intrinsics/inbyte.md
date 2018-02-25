---
title: __inbyte | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- __inbyte
- __inbyte_cpp
dev_langs:
- C++
helpviewer_keywords:
- in instruction
- __inbyte intrinsic
ms.assetid: 03b61799-2a08-474d-adc4-2cbf7c81a4d5
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c3acb6e5a5fc5f9f9a6808ae8b2047da32b1b2d4
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="inbyte"></a>__inbyte
**Microsoft-spezifisch**  
  
 Generiert die `in` -Anweisung, ein Byte zurückgeben Auslesen von angegebene Port `Port`.  
  
## <a name="syntax"></a>Syntax  
  
```  
unsigned char __inbyte(  
   unsigned short Port  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 [in] `Port`  
 Der Port, aus dem gelesen werden soll.  
  
## <a name="return-value"></a>Rückgabewert  
 Das gelesene Byte aus dem angegebenen Port.  
  
## <a name="requirements"></a>Anforderungen  
  
|Systemintern|Architektur|  
|---------------|------------------|  
|`__inbyte`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Headerdatei** \<intrin.h >  
  
**Ende Microsoft-spezifisch**  
  
## <a name="remarks"></a>Hinweise  
 Diese Routine ist nur als systeminterne Funktion verfügbar.  
  
## <a name="see-also"></a>Siehe auch  
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)