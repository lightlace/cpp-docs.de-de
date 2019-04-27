---
title: _get_fmode
ms.date: 11/04/2016
apiname:
- _get_fmode
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
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- get_fmode
- _get_fmode
helpviewer_keywords:
- _get_fmode function
- file translation [C++], default mode
- get_fmode function
ms.assetid: 22ea70e2-b9b5-422d-b514-64f4beaea45c
ms.openlocfilehash: dc4740b20ab7283dd8b9f73f458eaba34e582832
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62287561"
---
# <a name="getfmode"></a>_get_fmode

Ruft den Standarddateiübersetzungsmodus für Datei E/A-Vorgänge auf.

## <a name="syntax"></a>Syntax

```C
errno_t _get_fmode(
   int * pmode
);
```

### <a name="parameters"></a>Parameter

*pmode*<br/>
Ein Zeiger auf eine ganze Zahl mit dem aktuellen Standardmodus gefüllt werden soll: **_O_TEXT** oder **_O_BINARY**.

## <a name="return-value"></a>Rückgabewert

Gibt 0 (null) zurück, wenn der Vorgang erfolgreich war. Wenn ein Fehler auftritt, erscheint ein Fehlercode. Wenn *Pmode* ist **NULL**, wird der Handler für ungültige Parameter aufgerufen, siehe [Parametervalidierung](../../c-runtime-library/parameter-validation.md). Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, **Errno** nastaven NA hodnotu **EINVAL** und die Funktion gibt **EINVAL**.

## <a name="remarks"></a>Hinweise

Die Funktion legt die globale Variable [_fmode](../../c-runtime-library/fmode.md) fest. Diese Variable gibt den Standard-dateiübersetzungsmodus für beide auf niedriger Ebene und Streamen von e/a-Vorgänge, z. B. **_open**, **_pipe**, **Fopen**, und [ Freopen](freopen-wfreopen.md).

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|Optionaler Header|
|-------------|---------------------|---------------------|
|**_get_fmode**|\<stdlib.h>|\<fcntl.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

Siehe das Beispiel in [_set_fmode](set-fmode.md).

## <a name="see-also"></a>Siehe auch

[_fmode](../../c-runtime-library/fmode.md)<br/>
[_set_fmode](set-fmode.md)<br/>
[_setmode](setmode.md)<br/>
[Text- und Binärmodusdatei-E/A](../../c-runtime-library/text-and-binary-mode-file-i-o.md)<br/>
