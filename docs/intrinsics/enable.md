---
title: all_e | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- _enable
- _enable_cpp
dev_langs:
- C++
helpviewer_keywords:
- enable intrinsic
- _enable intrinsic
- ssm instruction
ms.assetid: 8bee669b-6bd8-4e25-9383-bb7d57295b4d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 86e6c8ba9fc1b4dff9b1ad947a770ae901937611
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="enable"></a>_enable
**Microsoft-spezifisch**  
  
 Ermöglicht Unterbrechungen.  
  
## <a name="syntax"></a>Syntax  
  
```  
void _enable(void);  
```  
  
## <a name="requirements"></a>Anforderungen  
  
|Systemintern|Architektur|  
|---------------|------------------|  
|`_enable`|x86, ARM, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Headerdatei** \<intrin.h >  
  
## <a name="remarks"></a>Hinweise  
 `_enable` weist den Prozessor an, das Interrupt-Flag festzulegen. Unter x86-Systemen erzeugt diese Funktion die Anweisung für das Set Interrupt Flag (`sti`).  
  
 Diese Funktion ist nur im Kernelmodus verfügbar. Wenn sie im Benutzermodus verwendet wird, wird eine privilegierte Anweisungsausnahme ausgelöst.  
  
**Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)