---
title: HUGE_VAL, _HUGE | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c2d763b8c5379223ddacb8077c463efa0b91acfa
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32390504"
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