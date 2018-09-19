---
title: _aktivieren | Microsoft-Dokumentation
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
ms.openlocfilehash: 3ca265bc8a6adc3da747e94ca67cd57749687f21
ms.sourcegitcommit: a41c4d096afca1e9b619bbbce045b77135d32ae2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2018
ms.locfileid: "42544457"
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
|`_enable`|X86, ARM, x64|  
  
 **Headerdatei** \<intrin.h >  
  
## <a name="remarks"></a>Hinweise  
 `_enable` weist den Prozessor an, das Interrupt-Flag festzulegen. Unter x86-Systemen erzeugt diese Funktion die Anweisung für das Set Interrupt Flag (`sti`).  
  
 Diese Funktion ist nur im Kernelmodus verfügbar. Wenn sie im Benutzermodus verwendet wird, wird eine privilegierte Anweisungsausnahme ausgelöst.  
  
**Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)