---
title: _open_osfhandle
ms.date: 05/21/2019
apiname:
- _open_osfhandle
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
- _open_osfhandle
- open_osfhandle
helpviewer_keywords:
- open_osfhandle function
- file handles [C++], associating
- _open_osfhandle function
ms.assetid: 30d94df4-7868-4667-a401-9eb67ecb7855
ms.openlocfilehash: 8527dade37f20b7341d5a26f5752ece668ab7fc9
ms.sourcegitcommit: bde3279f70432f819018df74923a8bb895636f81
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/23/2019
ms.locfileid: "66174800"
---
# <a name="openosfhandle"></a>_open_osfhandle

Ordnet den C-Laufzeit-Dateideskriptor einem vorhandenen Betriebssystem-Dateihandle zu.

## <a name="syntax"></a>Syntax

```cpp
int _open_osfhandle (
   intptr_t osfhandle,
   int flags
);
```

### <a name="parameters"></a>Parameter

*osfhandle*<br/>
Betriebssystem-Dateihandle.

*flags*<br/>
Zulässige Vorgangsarten.

## <a name="return-value"></a>Rückgabewert

Im Erfolgsfall gibt **_open_osfhandle** einen C-Laufzeit-Dateideskriptor zurück. Andernfalls wird -1 zurückgegeben.

## <a name="remarks"></a>Anmerkungen

Die **_open_osfhandle**-Funktion weist einen C-Laufzeit-Dateideskriptor zu und ordnet diesen der von *osfhandle* angegebenen Betriebssystem-Dateihandle zu. Um eine Compilerwarnung zu vermeiden, wandeln Sie das *osfhandle*-Argument von **HANDLE** zu **intptr_t** um. Das *flags*-Argument ist ein Ganzzahlausdruck, der von einer oder mehreren der folgenden Manifestkonstanten gebildet wurde, die in \<fcntl.h> definiert sind. Wenn zwei oder mehr Manifestkonstanten verwendet werden, um das *flags*-Argument zu bilden, werden die Konstanten mit dem bitweisen OR-Operator kombiniert ( **&#124;** ).

Die Manifestkonstanten werden in \<fcntl.h> definiert:

|||
|-|-|
| **\_O\_APPEND** | Positioniert einen Dateizeiger vor jedem Schreibvorgang am Ende der Datei. |
| **\_O\_RDONLY** | Öffnet eine Datei nur zum Lesen. |
| **\_O\_TEXT** | Öffnet eine Datei im Textmodus (übersetzt). |
| **\_O\_WTEXT** | Öffnet eine Datei in Unicode (übersetzt UTF-16). |

Der **_open_osfhandle**-Aufruf überträgt den Besitz am Win32-Dateihandle auf den Dateideskriptor. Um eine mit **_open_osfhandle** geöffnete Datei zu schließen, rufen Sie [\_close](close.md) auf. Das zugrundeliegende OS-Dateihandle wird auch mit einem **_close**-Aufruf geschlossen. Rufen Sie nicht die Win32-Funktion **CloseHandle** für das ursprüngliche Handle auf. Wenn der Dateideskriptor im Besitz eines **FILE &#42;** -Streams ist, dann werden durch einen Aufruf von [fclose](fclose-fcloseall.md) für diesen **FILE &#42;** -Stream sowohl der Dateideskriptor als auch das zugrunde liegende Handle geschlossen. In diesem Fall rufen Sie nicht **_close** für den Dateideskriptor oder **CloseHandle** für das ursprüngliche Handle auf.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**_open_osfhandle**|\<io.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[Dateibehandlung](../../c-runtime-library/file-handling.md)<br/>
