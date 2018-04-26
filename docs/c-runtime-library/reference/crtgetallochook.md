---
title: _CrtGetAllocHook | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _CrtGetAllocHook
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
apitype: DLLExport
f1_keywords:
- CrtGetAllocHook
- _CrtGetAllocHook
dev_langs:
- C++
helpviewer_keywords:
- _CrtGetAllocHook function
- CrtGetAllocHook function
ms.assetid: 036acf7c-547a-4b3f-a636-80451070d7ed
caps.latest.revision: 12
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6a0b1515e82d35159766993373f1dd6d8325f3b9
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2018
---
# <a name="crtgetallochook"></a>_CrtGetAllocHook

Ruft die aktuelle clientdefinierte Zuordnungsfunktion zur Verknüpfung mit dem Speicherbelegungsprozess der C-Laufzeit ab (nur Debugversion).

## <a name="syntax"></a>Syntax

```C
_CRT_ALLOC_HOOK _CrtGetAllocHook( void );
```

## <a name="return-value"></a>Rückgabewert

Gibt die momentan definierten Reservierungshookfunktion zurück.

## <a name="remarks"></a>Hinweise

**_CrtGetAllocHook** Ruft die aktuelle clientdefinierte anwendungshookfunktion für den speicherbelegungsprozess der C-Laufzeit-Bibliothek ab.

Weitere Informationen zur Verwendung anderer hookfähiger Laufzeitfunktionen und zum Schreiben eigener clientdefinierter Hookfunktionen finden Sie unter [Debug Hook Function Writing (Schreiben von Hookfunktionen zum Debuggen)](/visualstudio/debugger/debug-hook-function-writing).

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|
|-------------|---------------------|
|**_CrtGetAllocHook**|\<crtdbg.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Bibliotheken

Nur Debugversionen der [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).

## <a name="see-also"></a>Siehe auch

[Debugroutinen](../../c-runtime-library/debug-routines.md)<br/>
[_CrtSetAllocHook](crtsetallochook.md)<br/>
