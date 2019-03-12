---
title: _acmdln, _tcmdln, _wcmdln
ms.date: 11/04/2016
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
helpviewer_keywords:
- _wcmdln global variable
- wcmdln global variable
- _acmdln global variable
- _tcmdln global variable
- tcmdln global variable
- acmdln global variable
ms.assetid: 4fc0a6a0-3f93-420a-a19f-5276061ba539
ms.openlocfilehash: f4cacb512cb9b5bb6ea22f4dc4014ac2a2eeebe6
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/11/2019
ms.locfileid: "57747020"
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

## <a name="remarks"></a>Anmerkungen

Diese internen CRT-Variablen speichern die vollständige Befehlszeile. Sie sind in den exportierten Symbolen für die CRT verfügbar, aber nicht zur Verwendung in Ihrem Code vorgesehen. `_acmdln` speichert die Daten als Zeichenfolge. `_wcmdln` speichert die Daten als Breitzeichen-Zeichenfolge. `_tcmdln` kann als `_acmdln` oder `_wcmdln` definiert werden, abhängig davon, was angemessen ist.

## <a name="see-also"></a>Siehe auch

[Globale Variablen](../c-runtime-library/global-variables.md)
