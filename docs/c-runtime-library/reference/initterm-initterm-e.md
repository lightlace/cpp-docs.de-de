---
title: _initterm, _initterm_e
ms.date: 11/04/2016
apiname:
- _initterm_e
- _initterm
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _initterm_e
- initterm
- _initterm
- initterm_e
helpviewer_keywords:
- initterm function
- initterm_e function
- _initterm function
- _initterm_e function
ms.assetid: 85131efe-c747-429a-8897-bcdedb000172
ms.openlocfilehash: 65963e95507d4d6444ebcc9038b5b8cf797f9feb
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50620713"
---
# <a name="initterm-initterme"></a>_initterm, _initterm_e

Interne Methoden, die eine Tabelle von Funktionszeigern durchlaufen und sie initialisieren.

Der erste Zeiger ist die Anfangsposition in der Tabelle, und der zweite Zeiger ist die Endposition.

## <a name="syntax"></a>Syntax

```C
void __cdecl _initterm(
   PVFV *,
   PVFV *
);

int __cdecl _initterm_e(
   PVFV *,
   PVFV *
);
```

## <a name="return-value"></a>Rückgabewert

Ein Fehlercode ungleich null, wenn eine Initialisierung fehlschlägt und einen Fehler auslöst; 0, wenn kein Fehler auftritt.

## <a name="remarks"></a>Hinweise

Diese Methoden werden während der Initialisierung eines C++-Programms nur intern aufgerufen. Rufen Sie diese Methoden nicht in einem Programm auf.

Wenn diese Methoden eine Tabelle mit Funktionseinträgen durchlaufen, überspringen sie **NULL** Einträge und fortfahren.

## <a name="see-also"></a>Siehe auch

[Alphabetische Funktionsreferenz](crt-alphabetical-function-reference.md)<br/>
