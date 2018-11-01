---
title: _close
ms.date: 11/04/2016
apiname:
- _close
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
- _close
helpviewer_keywords:
- _close function
- close function
- files [C++], closing
ms.assetid: 4708a329-8acf-4cd9-b7b0-a952e1897247
ms.openlocfilehash: faea008903136e8abdc39297672b31800ada796d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50528023"
---
# <a name="close"></a>_close

Schließt eine Datei.

## <a name="syntax"></a>Syntax

```C
int _close(
   int fd
);
```

### <a name="parameters"></a>Parameter

*fd*<br/>
Dateideskriptor, der auf die geöffnete Datei verweist.

## <a name="return-value"></a>Rückgabewert

**_close** gibt 0 zurück, wenn die Datei erfolgreich geschlossen wurde. Ein Rückgabewert 1 gibt einen Fehler.

## <a name="remarks"></a>Hinweise

Die **_close** -Funktion schließt die zugeordnete Datei *fd*.

Der Dateideskriptor und das zugrunde liegende Betriebssystem-Dateihandle werden geschlossen. Folglich ist es nicht notwendig, **"CloseHandle"** wird die Datei ursprünglich geöffnet wurde, mithilfe der Win32-Funktion **CreateFile** und konvertiert Sie in eine Sicherheitsbeschreibung **_open_osfhandle**.

Diese Funktion überprüft ihre Parameter. Wenn *fd* ein fehlerhafter Dateideskriptor, wird der Handler für ungültige Parameter aufgerufen, siehe [Parametervalidierung](../../c-runtime-library/parameter-validation.md). Wenn die weitere Ausführung zugelassen wird, gibt die Funktionen-1 zurück und **Errno** nastaven NA hodnotu **EBADF**.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|Optionaler Header|
|-------------|---------------------|---------------------|
|**_close**|\<io.h>|\<errno.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

Siehe das Beispiel für [_open](open-wopen.md).

## <a name="see-also"></a>Siehe auch

[E/A auf niedriger Ebene](../../c-runtime-library/low-level-i-o.md)<br/>
[_chsize](chsize.md)<br/>
[_creat, _wcreat](creat-wcreat.md)<br/>
[_dup, _dup2](dup-dup2.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
[_unlink, _wunlink](unlink-wunlink.md)<br/>
