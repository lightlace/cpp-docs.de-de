---
title: __readmsr | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- __readmsr
dev_langs:
- C++
helpviewer_keywords:
- Read Model Specific Register
- rdmsr instruction
- __readmsr intrinsic
ms.assetid: 7ab1f8e8-72cb-4ce4-817d-3e728a3c9716
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 24720a6a11809dfb47d8fd10a2f0efa4c2aa73ab
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="readmsr"></a>__readmsr
**Microsoft-spezifisch**  
  
 Generiert die `rdmsr` -Anweisung, die das modellspezifischen Register gemäß liest `register` und den Wert zurückgibt.  
  
## <a name="syntax"></a>Syntax  
  
```  
__int64 __readmsr(   
   int register   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 [in] `register`  
 Das Modell bestimmte Register zu lesen.  
  
## <a name="return-value"></a>Rückgabewert  
 Der Wert im angegebenen registrieren.  
  
## <a name="requirements"></a>Anforderungen  
  
|Systemintern|Architektur|  
|---------------|------------------|  
|`__readmsr`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Headerdatei** \<intrin.h >  
  
## <a name="remarks"></a>Hinweise  
 Diese Funktion ist nur im Kernelmodus verfügbar, und die Routine ist nur als systeminterne Funktion verfügbar.  
  
 Weitere Informationen finden Sie in der AMD-Dokumentation.  
  
**Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)