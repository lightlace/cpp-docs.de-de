---
title: _initterm, _initterm_e | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- initterm function
- initterm_e function
- _initterm function
- _initterm_e function
ms.assetid: 85131efe-c747-429a-8897-bcdedb000172
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 470ad6cbf13efb170f61aa12f7859f2baa248c2b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
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

Wenn diese Methoden auf eine Tabelle mit der Funktion Einträge abzuarbeiten, überspringen sie **NULL** Einträge und den Vorgang fortzusetzen.

## <a name="see-also"></a>Siehe auch

[Alphabetische Funktionsreferenz](crt-alphabetical-function-reference.md)<br/>
