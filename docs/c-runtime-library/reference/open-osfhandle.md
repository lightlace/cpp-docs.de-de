---
title: _open_osfhandle
ms.date: 05/29/2018
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
ms.openlocfilehash: e8b7dc097c1af60894c627b8b660c4d9d81361db
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50519456"
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

Im Erfolgsfall **_open_osfhandle** gibt einen C-Laufzeit-Dateideskriptor zurück. Andernfalls wird-1 zurückgegeben.

## <a name="remarks"></a>Hinweise

Die **_open_osfhandle** Funktion weist einen C-Laufzeit-Dateideskriptor und ordnet sie den Betriebssystem Dateihandle, das gemäß *Osfhandle*. Um eine compilerwarnung zu vermeiden, wandeln die *Osfhandle* Argument von **BEHANDELN** zu **Intptr_t**. Die *Flags* Argument ist ein Ganzzahlausdruck, der von einem oder mehreren Manifestkonstanten in definierten \<fcntl.h >. Wenn zwei oder mehr Manifestkonstanten verwendet werden, zu der *Flags* -Argument, werden die Konstanten mit dem bitweisen OR-Operator kombiniert ( **&#124;** ).

Sind diese Manifestkonstanten in definiert \<fcntl.h >:

|||
|-|-|
**\_O\_ANFÜGEN**|Positioniert einen Dateizeiger vor jedem Schreibvorgang am Ende der Datei.
**\_O\_RDONLY**|Öffnet eine Datei nur zum Lesen.
**\_O\_TEXT**|Öffnet eine Datei im Textmodus (übersetzt).
**\_O\_WTEXT**|Öffnet eine Datei in Unicode (übersetzt UTF-16).

Die **_open_osfhandle** Aufruf überträgt den Besitz des Win32-Dateihandles auf den Dateideskriptor. Eine mit geöffnete Datei schließen **_open_osfhandle**, rufen Sie [ \_schließen](close.md). Das zugrunde liegende Betriebssystem-Dateihandle ist ebenfalls geschlossen, durch einen Aufruf von **_close**, daher es nicht notwendig ist, die Win32-Funktion **"CloseHandle"** am ursprünglichen Handle. Wenn der Dateideskriptor Besitz ist eine **Datei &#42;**  Stream, rufen Sie dann [Fclose](fclose-fcloseall.md) auf, die **Datei &#42;**  Stream schließt außerdem sowohl den Dateideskriptor und das zugrunde liegende Handle. Rufen Sie in diesem Fall nicht **_close** auf den Dateideskriptor.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**_open_osfhandle**|\<io.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[Dateibehandlung](../../c-runtime-library/file-handling.md)<br/>
