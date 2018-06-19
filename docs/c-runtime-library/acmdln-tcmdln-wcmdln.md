---
title: _acmdln, _tcmdln, _wcmdln | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
apiname:
- _wcmdln
- _acmdln
apilocation:
- msvcrt.dll
apitype: DLLExport
f1_keywords:
- _acmdln
- acmdln
- _wcmdln
- wcmdln
- _tcmdln
- tcmdln
dev_langs:
- C++
helpviewer_keywords:
- _wcmdln global variable
- wcmdln global variable
- _acmdln global variable
- _tcmdln global variable
- tcmdln global variable
- acmdln global variable
ms.assetid: 4fc0a6a0-3f93-420a-a19f-5276061ba539
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 141e261af618cc6058a2a731b70e824582be303b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32386494"
---
# <a name="acmdln-tcmdln-wcmdln"></a>_acmdln, _tcmdln, _wcmdln
Interne globale CRT-Variable. Die Befehlszeile.  
  
## <a name="syntax"></a>Syntax  
  
```  
char * _acmdln;  
wchar_t * _wcmdln;  
  
#ifdef WPRFLAG  
   #define _tcmdln _wcmdln  
#else  
   #define _tcmdln _acmdln  
```  
  
## <a name="remarks"></a>Hinweise  
 Diese internen CRT-Variablen speichern die vollständige Befehlszeile. Sie sind in den exportierten Symbolen für die CRT verfügbar, aber nicht zur Verwendung in Ihrem Code vorgesehen. `_acmdln` speichert die Daten als Zeichenfolge. `_wcmdln` speichert die Daten als Breitzeichen-Zeichenfolge. `_tcmdln` kann als `_acmdln` oder `_wcmdln` definiert werden, abhängig davon, was angemessen ist.  
  
## <a name="see-also"></a>Siehe auch  
 [Globale Variablen](../c-runtime-library/global-variables.md)