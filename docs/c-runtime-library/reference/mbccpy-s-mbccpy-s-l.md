---
title: _mbccpy_s, _mbccpy_s_l | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _mbccpy_s
- _mbccpy_s_l
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
- api-ms-win-crt-multibyte-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _mbccpy_s_l
- mbccpy_s_l
- mbccpy_s
- _mbccpy_s
dev_langs:
- C++
helpviewer_keywords:
- tccpy_s_l function
- _tccpy_s function
- _mbccpy_s function
- mbccpy_s function
- tccpy_s function
- mbccpy_s_l function
- _tccpy_s_l function
- _mbccpy_s_l function
ms.assetid: b6e965fa-53c1-4ec3-85ef-a1c4b4f2b2da
caps.latest.revision: 30
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5c396422fefff8a7d7da49517ae2f8ea1a06e7fd
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2018
---
# <a name="mbccpys-mbccpysl"></a>_mbccpy_s, _mbccpy_s_l

Kopiert ein Multibytezeichen von einer Zeichenfolge in eine andere Zeichenfolge. Diese Versionen von [_mbccpy, _mbccpy_l](mbccpy-mbccpy-l.md) enthalten Sicherheitserweiterungen, wie unter [Sicherheitserweiterungen in der CRT](../../c-runtime-library/security-features-in-the-crt.md) beschrieben.

> [!IMPORTANT]
> Diese API kann nicht in Anwendungen verwendet werden, die in Windows-Runtime ausgeführt werden. Weitere Informationen finden Sie im Artikel [CRT functions not supported in Universal Windows Platform apps (In Apps für die universelle Windows-Plattform nicht unterstützte CRT-Funktionen)](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Syntax

```C
errno_t _mbccpy_s(
   unsigned char *dest,
   size_t buffSizeInBytes,
   int * pCopied,
   const unsigned char *src
);
errno_t _mbccpy_s_l(
   unsigned char *dest,
   size_t buffSizeInBytes,
   int * pCopied,
   const unsigned char *src,
   locale_t locale
);
template <size_t size>
errno_t _mbccpy_s(
   unsigned char (&dest)[size],
   int * pCopied,
   const unsigned char *src
); // C++ only
template <size_t size>
errno_t _mbccpy_s_l(
   unsigned char (&dest)[size],
   int * pCopied,
   const unsigned char *src,
   locale_t locale
); // C++ only
```

### <a name="parameters"></a>Parameter

*dest*<br/>
Kopierziel.

*buffSizeInBytes*<br/>
Größe des Zielpuffers.

*pCopied*<br/>
Wird mit der Anzahl kopierter Bytes gefüllt (bei Erfolg 1 oder 2). Übergeben Sie **NULL** Wenn Sie über die Anzahl nicht relevant ist.

*src*<br/>
Zu kopierendes Multibytezeichen.

*locale*<br/>
Zu verwendendes Gebietsschema.

## <a name="return-value"></a>Rückgabewert

Null, wenn erfolgreich, ein Fehlercode, wenn ein Fehler auftritt. Wenn *Src* oder *Dest* ist **NULL**, oder wenn mehr als **BuffSizeinBytes** Bytes kopiert werden, um *Dest*, wird der Handler für ungültige Parameter aufgerufen wird, wie in beschrieben, [Parametervalidierung](../../c-runtime-library/parameter-validation.md). Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, der Funktionen zurück **EINVAL** und **Errno** festgelegt ist, um **EINVAL**.

## <a name="remarks"></a>Hinweise

Die **_mbccpy_s** -Funktion kopiert ein Multibytezeichen von *Src* auf *Dest*. Wenn *Src* verweist nicht auf das führende Byte eines multibytezeichens von einen impliziten Aufruf bestimmt [_ismbblead](ismbblead-ismbblead-l.md), dann wird das einzelne Byte, *Src* zeigt, kopiert. Wenn *Src* verweist auf ein führendes Byte ist, aber das nächste Byte 0 und somit ungültig ist, dann 0 in kopiert *Dest*, **Errno** festgelegt ist, um **EILSEQ**, und die Funktion gibt **EILSEQ**.

**_mbccpy_s** fügt keinen null-Abschlusszeichen, aber wenn *Src* verweist auf ein Null-Zeichen, wird diese Null in kopiert *Dest* (Dies ist nur eine reguläre einzelbytekopie).

Der Wert in *pCopied* mit der Anzahl kopierter Bytes gefüllt wird. Mögliche Werte sind 1 und 2, wenn der Vorgang erfolgreich ist. Wenn **NULL** übergeben wird, wird dieser Parameter ignoriert.

|*src*|kopiert *Dest*|*pCopied*|Rückgabewert|
|-----------|----------------------|---------------|------------------|
|kein führendes Byte|kein führendes Byte|1|0|
|0|0|1|0|
|führendes Byte gefolgt von Nicht-0|führendes Byte gefolgt von Nicht-0|2|0|
|führendes Byte gefolgt von 0|0|1|**EILSEQ**|

Beachten Sie, dass die zweite Zeile nur ein Sonderfall der ersten ist. Beachten Sie außerdem, die die Tabelle annimmt *BuffSizeInBytes* >= *pCopied*.

**_mbccpy_s** verwendet das aktuelle Gebietsschema für jedes vom Gebietsschema abhängiges Verhalten. **_mbccpy_s_l** ist identisch mit **_mbccpy_s** mit dem Unterschied, dass **_mbccpy_s_l** verwendet das Gebietsschema für jedes gebietsschemaabhängige Verhalten übergeben.

Die Verwendung dieser Funktionen in C++ wird durch Überladungen (als Vorlagen vorhanden) vereinfacht. Überladungen können automatisch die Pufferlänge ableiten, sodass kein Größenargument angegeben werden muss. Weitere Informationen finden Sie unter [Secure Template Overloads (Sichere Vorlagenüberladungen)](../../c-runtime-library/secure-template-overloads.md).

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|Tchar.h-Routine|_UNICODE und _MBCS nicht definiert|_MBCS definiert|_UNICODE definiert|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tccpy_s**|Führt eine Zuordnung zum Makro oder zur Inlinefunktion aus.|**_mbccpy_s**|Führt eine Zuordnung zum Makro oder zur Inlinefunktion aus.|

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|
|-------------|---------------------|
|**_mbccpy_s**|\<mbstring.h>|
|**_mbccpy_s_l**|\<mbstring.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[Locale](../../c-runtime-library/locale.md)<br/>
[Interpretation von Multibyte-Zeichensequenzen](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[_mbclen, mblen, _mblen_l](mbclen-mblen-mblen-l.md)<br/>
