---
title: fsetpos | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- streams, setting position indicators
- fsetpos function
ms.assetid: 6d19ff48-1a2b-47b3-9f23-ed0a47b5a46e
caps.latest.revision: 12
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0ceacacbe029488995c47e305682b56751347591
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2018
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

*Stream*<br/>
Zeiger auf die **FILE**-Struktur.

*POS*<br/>
Speicher des Positionsindikators

## <a name="return-value"></a>Rückgabewert

Im Erfolgsfall **Fsetpos** gibt 0 zurück. Bei einem Fehler, die Funktion gibt einen Wert ungleich NULL zurück und legt **Errno** auf einen der folgenden Manifestkonstanten (definiert in ERRNO. H): **EBADF**, d. h. die Datei kann nicht zugegriffen werden oder das Objekt, *Stream* verweist, ist keine gültige Dateistruktur; oder **EINVAL**, was bedeutet, dass einen ungültigen Wert für *Stream* oder *pos* übergeben wurde. Wenn ein ungültiger Parameter übergeben wird, rufen diese Funktionen den Handler für ungültige Parameter auf, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben wird.

Weitere Informationen zu diesen und anderen Rückgabecodes finden Sie unter [_doserrno, errno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Hinweise

Die **Fsetpos** Funktion legt der dateipositionszeiger für *Stream* auf den Wert der *pos*, erhalten Sie in einem vorherigen Aufruf für **Fgetpos**gegen *Stream*. Die Funktion löscht den Dateiende-Indikator und macht alle mit dem [Ungetc](ungetc-ungetwc.md) auf *Stream*. Nach dem Aufruf **Fsetpos**, auf den nächsten Vorgang *Stream* werden möglicherweise entweder Eingabe oder Ausgabe.

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
