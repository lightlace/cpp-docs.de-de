---
title: fsetpos
ms.date: 11/04/2016
apiname:
- fsetpos
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
- fsetpos
helpviewer_keywords:
- streams, setting position indicators
- fsetpos function
ms.assetid: 6d19ff48-1a2b-47b3-9f23-ed0a47b5a46e
ms.openlocfilehash: 9854c71e381da6ec9a75d440b9588e2476bada7c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62287572"
---
# <a name="fsetpos"></a>fsetpos

Legt den Indikator für die Position im Stream fest

## <a name="syntax"></a>Syntax

```C
int fsetpos(
   FILE *stream,
   const fpos_t *pos
);
```

### <a name="parameters"></a>Parameter

*stream*<br/>
Zeiger auf die **FILE**-Struktur.

*pos*<br/>
Speicher des Positionsindikators

## <a name="return-value"></a>Rückgabewert

Im Erfolgsfall **Fsetpos** gibt 0 zurück. Bei einem Fehler, die Funktion gibt einen Wert ungleich NULL zurück und legt **Errno** auf eine der folgenden Manifestkonstanten, die (definiert in ERRNO. H): **EBADF**, das bedeutet, dass die Datei kann nicht zugegriffen werden oder das Objekt, das *Stream* verweist, ist keine gültige Dateistruktur hat; oder **EINVAL**, was bedeutet, dass einen ungültigen Wert für *Stream*  oder *pos* übergeben wurde. Wenn ein ungültiger Parameter übergeben wird, rufen diese Funktionen den Handler für ungültige Parameter auf, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben wird.

Weitere Informationen zu diesen und anderen Rückgabecodes finden Sie unter [_doserrno, errno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Hinweise

Die **Fsetpos** Funktion legt den dateipositionszeiger für *Stream* auf den Wert der *pos*, erhalten Sie in einem vorherigen Aufruf von **Fgetpos**für *Stream*. Die Funktion löscht den Dateiende-Indikator und macht alle Effekte von [Ungetc](ungetc-ungetwc.md) auf *Stream*. Nach dem Aufruf **Fsetpos**, der nächste Vorgang *Stream* unter Umständen werden entweder eine Eingabe oder Ausgabe.

## <a name="requirements"></a>Anforderungen

|Funktion|Erforderlicher Header|
|--------------|---------------------|
|**fsetpos**|\<stdio.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

Siehe das Beispiel für [fgetpos](fgetpos.md)

## <a name="see-also"></a>Siehe auch

[Stream-E/A](../../c-runtime-library/stream-i-o.md)<br/>
[fgetpos](fgetpos.md)<br/>
