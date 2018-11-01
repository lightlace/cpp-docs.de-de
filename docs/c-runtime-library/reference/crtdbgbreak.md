---
title: _CrtDbgBreak
ms.date: 11/04/2016
apiname:
- _CrtDbgBreak
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
- _CrtDbgBreak
- CrtDbgBreak
helpviewer_keywords:
- CrtDbgBreak function
- _CrtDbgBreak function
ms.assetid: 01f8b4a2-a2c7-4e1f-9f39-e573b4a7871f
ms.openlocfilehash: 4cf64daaea3193f7cf6b3aaa0b1aab031f104704
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50478300"
---
# <a name="crtdbgbreak"></a>_CrtDbgBreak

Legt einen Haltepunkt in einer bestimmten Zeile des Codes (Nur im Debugmodus aktiviert)

## <a name="syntax"></a>Syntax

```C
void _CrtDbgBreak( void );
```

## <a name="return-value"></a>Rückgabewert

Es ist kein Rückgabewert vorhanden.

## <a name="remarks"></a>Hinweise

Die **_CrtDbgBreak** Funktion Debuggen legt einen Haltepunkt fest in der bestimmten Zeile des Codes, in dem sich die Funktion befindet. Diese Funktion wird nur im Debugmodus verwendet und ist abhängig von **_DEBUG** , was zuvor definiert.

Weitere Informationen zur Verwendung anderer hookfähiger Laufzeitfunktionen und zum Schreiben eigener clientdefinierter Hookfunktionen finden Sie unter [Writing Your Own Debug Hook Functions (Schreiben von Hookfunktionen zum Debuggen)](/visualstudio/debugger/debug-hook-function-writing).

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**_CrtDbgBreak**|\<CRTDBG.h>|

## <a name="libraries"></a>Bibliotheken

Nur Debugversionen der [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).

## <a name="see-also"></a>Siehe auch

[Debugroutinen](../../c-runtime-library/debug-routines.md)<br/>
[__debugbreak](../../intrinsics/debugbreak.md)<br/>
