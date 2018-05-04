---
title: fwrite | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- fwrite
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
- fwrite
dev_langs:
- C++
helpviewer_keywords:
- streams, writing data to
- fwrite function
ms.assetid: 7afacf3a-72d7-4a50-ba2e-bea1ab9f4124
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f1320bcc61830833f2b1a4a225dff30652df2d3a
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="fwrite"></a>fwrite

Schreibt Daten in einen Stream.

## <a name="syntax"></a>Syntax

```C
size_t fwrite(
   const void *buffer,
   size_t size,
   size_t count,
   FILE *stream
);
```

### <a name="parameters"></a>Parameter

*buffer*<br/>
Zeiger auf die zu schreibenden Daten.

*size*<br/>
Elementgröße in Bytes.

*count*<br/>
Maximale Anzahl zu schreibender Elemente.

*Stream*<br/>
Zeiger auf die **FILE**-Struktur.

## <a name="return-value"></a>Rückgabewert

**Fwrite** gibt die Anzahl der vollständigen Elemente, die tatsächlich geschrieben werden, was u. u. nicht kleiner als *Anzahl* , wenn ein Fehler auftritt. Außerdem kann im Fall eines Fehlers möglicherweise der Dateipositionszeiger nicht bestimmt werden. Wenn entweder *Stream* oder *Puffer* ein null-Zeiger ist oder wenn eine ungerade Anzahl von zu schreibenden Bytes im Unicode-Modus angegeben wird, ruft die Funktion des Handlers für ungültige Parameter an, wie in beschrieben [ Überprüfen der Parameter](../../c-runtime-library/parameter-validation.md). Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, setzt diese Funktion **Errno** auf **EINVAL** und gibt 0 zurück.

## <a name="remarks"></a>Hinweise

Die **Fwrite** -Funktion schreibt bis zu *Anzahl* Elemente, von *Größe* Länge, die jeweils aus *Puffer* an die Ausgabe *Stream*. Der Dateizeiger zugeordneten *Stream* (sofern vorhanden) wird durch die Anzahl der tatsächlich geschriebenen Bytes erhöht. Wenn *Stream* öffnen im Textmodus wird jeder Zeilenvorschub durch einen Wagenrücklauf - Zeilenvorschub ersetzt. Diese Ersetzung hat keine Auswirkung auf den Rückgabewert.

Wenn *Stream* im Unicode-Übersetzungsmodus geöffnet wird – z. B. wenn *Stream* geöffnet wird, durch den Aufruf **Fopen** und mit einem Modusparameter, die enthält **ccs- = UNICODE**, **ccs = UTF-16LE**, oder **ccs-UTF-8 =**, oder wenn der Modus in eine Unicode-Übersetzungsmodus geändert wird, mit **_setmode** und einen Modus Parameter, der enthält **_O_WTEXT**, **_O_U16TEXT**, oder **_O_U8TEXT**–*Puffer* interpretiert als Zeiger auf ein Array von **Wchar_t** , UTF-16-Daten enthält. Der Versuch, in diesem Modus eine ungerade Anzahl von Bytes zu schreiben, führt zu einem Parametervalidierungsfehler.

Da diese Funktion den aufrufenden Thread sperrt, ist sie threadsicher. Eine nicht sperrende Version finden Sie unter **_fwrite_nolock**.

## <a name="requirements"></a>Anforderungen

|Funktion|Erforderlicher Header|
|--------------|---------------------|
|**fwrite**|\<stdio.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

Ein Beispiel hierfür finden Sie unter [fread](fread.md).

## <a name="see-also"></a>Siehe auch

[Stream-E/A](../../c-runtime-library/stream-i-o.md)<br/>
[_setmode](setmode.md)<br/>
[fread](fread.md)<br/>
[_fwrite_nolock](fwrite-nolock.md)<br/>
[_write](write.md)<br/>
