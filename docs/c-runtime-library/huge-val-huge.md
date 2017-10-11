---
title: HUGE_VAL, _HUGE | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _HUGE
apilocation:
- msvcrt.dll
apitype: DLLExport
f1_keywords:
- _HUGE
- HUGE_VAL
dev_langs:
- C++
helpviewer_keywords:
- _HUGE constant
- HUGE_VAL constant
- double value
ms.assetid: 3f044b45-02cd-46b2-b1de-87fd0441dd6a
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 4c3ea9b33c4eae9d39f4df49140dcc14db1a660e
ms.contentlocale: de-de
ms.lasthandoff: 10/09/2017

---
# <a name="hugeval-huge"></a>HUGE_VAL, _HUGE
## <a name="syntax"></a>Syntax  
  
```  
  
#include <math.h>  
  
```  
  
## <a name="remarks"></a>Hinweise  
 `HUGE_VAL` ist der größte darstellbare Double-Wert. Dieser Wert wird durch viele mathematische Laufzeitfunktionen zurückgegeben, wenn ein Fehler auftritt. Für einige Funktionen wird -`HUGE_VAL` zurückgegeben. `HUGE_VAL` wird als `_HUGE` definiert, aber die mathematischen Laufzeitfunktionen geben `HUGE_VAL` zurück. Verwenden Sie der Konsistenz wegen außerdem `HUGE_VAL` in Ihrem Code.  
  
## <a name="see-also"></a>Siehe auch  
 [Globale Konstanten](../c-runtime-library/global-constants.md)
