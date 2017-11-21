---
title: all_e | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- _enable
- _enable_cpp
dev_langs: C++
helpviewer_keywords:
- enable intrinsic
- _enable intrinsic
- ssm instruction
ms.assetid: 8bee669b-6bd8-4e25-9383-bb7d57295b4d
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: e839a70f106ec83c9d2ee786c20f68817e0d4be6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
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