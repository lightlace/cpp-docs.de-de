---
title: _get_wpgmptr
ms.date: 11/04/2016
apiname:
- _get_wpgmptr
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
- get_wpgmptr
- _get_wpgmptr
helpviewer_keywords:
- _wpgmptr global variable
- get_wpgmptr function
- wpgmptr global variable
- _get_wpgmptr function
ms.assetid: a77cdd13-2303-4b7c-9a60-8debdbef2011
ms.openlocfilehash: 87738c8564b70df37a9f2fbdcc5e5ab80165af32
ms.sourcegitcommit: 1819bd2ff79fba7ec172504b9a34455c70c73f10
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/09/2018
ms.locfileid: "51329084"
---
# <a name="getwpgmptr"></a>_get_wpgmptr

Ruft den aktuellen Wert des der **_wpgmptr** globale Variable.

## <a name="syntax"></a>Syntax

```C
errno_t _get_wpgmptr(
   wchar_t **pValue
);
```

### <a name="parameters"></a>Parameter

*pValue*<br/>
Ein Zeiger auf eine Zeichenfolge, die mit den aktuellen Wert der gefüllt werden die **_wpgmptr** Variable.

## <a name="return-value"></a>Rückgabewert

Gibt 0 (null) zurück, wenn der Vorgang erfolgreich war. Wenn ein Fehler auftritt, erscheint ein Fehlercode. Wenn *pValue* ist **NULL**, wird der Handler für ungültige Parameter aufgerufen, siehe [Parametervalidierung](../../c-runtime-library/parameter-validation.md). Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, setzt diese Funktion **Errno** zu **EINVAL** und gibt **EINVAL**.

## <a name="remarks"></a>Hinweise

Rufen Sie nur **_get_wpgmptr** , wenn das Programm einen Einstiegspunkt für die Breite aufweist, wie **wmain()** oder **wWinMain()**. Die **_wpgmptr** globale Variable enthält den vollständigen Pfad der ausführbaren Datei, die dem Prozess als Breitzeichen-Zeichenfolge zugeordnet. Weitere Informationen finden Sie unter [_pgmptr, _wpgmptr](../../c-runtime-library/pgmptr-wpgmptr.md).

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**_get_wpgmptr**|\<stdlib.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[_get_pgmptr](get-pgmptr.md)<br/>
