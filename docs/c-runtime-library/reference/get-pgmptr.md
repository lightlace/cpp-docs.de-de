---
title: _get_pgmptr
ms.date: 11/04/2016
apiname:
- _get_pgmptr
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
- get_pgmptr
- _get_pgmptr
helpviewer_keywords:
- get_pgmptr function
- _get_pgmptr function
- pgmptr global variable
- _pgmptr global variable
ms.assetid: 29f16a9f-a685-4721-add3-7fad4f67eece
ms.openlocfilehash: 40c9f237aadb5f44066bcbf40fe378fb2ce96fc5
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50562499"
---
# <a name="getpgmptr"></a>_get_pgmptr

Ruft den aktuellen Wert des der **_pgmptr** globale Variable.

## <a name="syntax"></a>Syntax

```C
errno_t _get_pgmptr( 
   char **pValue 
);
```

### <a name="parameters"></a>Parameter

*pValue*<br/>
Ein Zeiger auf eine Zeichenfolge, die mit den aktuellen Wert der gefüllt werden die **_pgmptr** Variable.

## <a name="return-value"></a>Rückgabewert

Gibt 0 (null) zurück, wenn der Vorgang erfolgreich war. Wenn ein Fehler auftritt, erscheint ein Fehlercode. Wenn *pValue* ist **NULL**, wird der Handler für ungültige Parameter aufgerufen, siehe [Parametervalidierung](../../c-runtime-library/parameter-validation.md). Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, setzt diese Funktion **Errno** zu **EINVAL** und gibt **EINVAL**.

## <a name="remarks"></a>Hinweise

Rufen Sie nur **_get_pgmptr** Wenn Ihr Programm einen Einstiegspunkt für die schmale verfügt, z.B. **main()** oder **WinMain()**. Die **_pgmptr** globale Variable enthält den vollständigen Pfad der ausführbaren Datei, die dem Prozess zugeordnet. Weitere Informationen finden Sie unter [_pgmptr, _wpgmptr](../../c-runtime-library/pgmptr-wpgmptr.md).

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**_get_pgmptr**|\<stdlib.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[_get_wpgmptr](get-wpgmptr.md)<br/>
