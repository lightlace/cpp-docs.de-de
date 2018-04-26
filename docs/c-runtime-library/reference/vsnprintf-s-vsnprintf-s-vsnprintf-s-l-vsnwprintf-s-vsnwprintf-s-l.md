---
title: vsnprintf_s, _vsnprintf_s, _vsnprintf_s_l, _vsnwprintf_s, _vsnwprintf_s_l | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _vsnwprintf_s
- _vsnwprintf_s_l
- _vsnprintf_s
- vsnprintf_s
- _vsnprintf_s_l
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
- ntdll.dll
- ucrtbase.dll
apitype: DLLExport
f1_keywords:
- _vsnprintf_s
- _vsntprintf_s
- _vsnwprintf_s
dev_langs:
- C++
helpviewer_keywords:
- vsnwprintf_s function
- _vsntprintf_s function
- _vsntprintf_s_l function
- vsntprintf_s function
- vsnwprintf_s_l function
- vsnprintf_s_l function
- vsntprintf_s_l function
- _vsnwprintf_s_l function
- _vsnprintf_s function
- vsnprintf_s function
- _vsnprintf_s_l function
- _vsnwprintf_s function
- formatted text [C++]
ms.assetid: 147ccfce-58c7-4681-a726-ef54ac1c604e
caps.latest.revision: 30
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 230f60f33f37f1151af693f4de585bf78703e983
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2018
---
# <a name="vsnprintfs-vsnprintfs-vsnprintfsl-vsnwprintfs-vsnwprintfsl"></a>vsnprintf_s, _vsnprintf_s, _vsnprintf_s_l, _vsnwprintf_s, _vsnwprintf_s_l

Schreiben von formatierter Ausgabe mithilfe eines Zeigers, der auf eine Liste von Argumenten zeigt. Dies sind Versionen von [vsnprintf, _vsnprintf, _vsnprintf_l, _vsnwprintf, _vsnwprintf_l](vsnprintf-vsnprintf-vsnprintf-l-vsnwprintf-vsnwprintf-l.md) mit Sicherheitsverbesserungen, wie in [Sicherheitsfunktionen in der CRT](../../c-runtime-library/security-features-in-the-crt.md) beschrieben.

## <a name="syntax"></a>Syntax

```C
int vsnprintf_s(
   char *buffer,
   size_t sizeOfBuffer,
   size_t count,
   const char *format,
   va_list argptr
);
int _vsnprintf_s(
   char *buffer,
   size_t sizeOfBuffer,
   size_t count,
   const char *format,
   va_list argptr
);
int _vsnprintf_s_l(
   char *buffer,
   size_t sizeOfBuffer,
   size_t count,
   const char *format,
   locale_t locale,
   va_list argptr
);
int _vsnwprintf_s(
   wchar_t *buffer,
   size_t sizeOfBuffer,
   size_t count,
   const wchar_t *format,
   va_list argptr
);
int _vsnwprintf_s_l(
   wchar_t *buffer,
   size_t sizeOfBuffer,
   size_t count,
   const wchar_t *format,
   locale_t locale,
   va_list argptr
);
template <size_t size>
int _vsnprintf_s(
   char (&buffer)[size],
   size_t count,
   const char *format,
   va_list argptr
); // C++ only
template <size_t size>
int _vsnwprintf_s(
   wchar_t (&buffer)[size],
   size_t count,
   const wchar_t *format,
   va_list argptr
); // C++ only
```

### <a name="parameters"></a>Parameter

*buffer*<br/>
Speicherort für die Ausgabe.

*sizeOfBuffer*<br/>
Die Größe der *Puffer* für die Ausgabe als die Anzahl der Zeichen.

*count*<br/>
Die maximale Anzahl von zu schreibenden Zeichen (ohne das abschließende Zeichen NULL) oder [_TRUNCATE](../../c-runtime-library/truncate.md).

*format*<br/>
Formatangabe.

*argptr*<br/>
Zeiger zur Liste der Argumente.

*locale*<br/>
Das zu verwendende Gebietsschema.

Weitere Informationen finden Sie unter [Formatangaben](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md).

## <a name="return-value"></a>Rückgabewert

**Vsnprintf_s**, **_vsnprintf_s** und **_vsnwprintf_s** Zurückgeben der Anzahl der Zeichen geschrieben, ohne das abschließende Null-Zeichen oder einen negativen Wert, wenn ein Ausgabefehler auftritt. **Vsnprintf_s** ist identisch mit **_vsnprintf_s**. **Vsnprintf_s** wird aus Gründen der Kompatibilität mit ANSI-Standard. **_vnsprintf** wird aus Gründen der Abwärtskompatibilität beibehalten.

Wenn der Speicher erforderlich, die zum Speichern der Daten und ein abschließendes Nullzeichen überschreitet *SizeOfBuffer*, Handler für ungültige Parameter aufgerufen, wie in beschrieben [Parametervalidierung](../../c-runtime-library/parameter-validation.md), es sei denn, *Anzahl*  ist [_TRUNCATE](../../c-runtime-library/truncate.md), in diesem Fall größtmöglicher Teil der Zeichenfolge als passt *Puffer* geschrieben wurde und-1 zurückgegeben. Wenn die Ausführung nach dem Handler für ungültige Parameter fortgesetzt wird, legen diese Funktionen *Puffer* auf eine leere Zeichenfolge festgelegt **Errno** auf **ERANGE**, und geben-1 zurück.

Wenn *Puffer* oder *Format* ist ein **NULL** -Zeiger ist, oder wenn *Anzahl* ist kleiner als oder gleich 0 ist, wird der Handler für ungültige Parameter aufgerufen. Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, legen diese Funktionen **Errno** auf **EINVAL** und geben-1 zurück.

### <a name="error-conditions"></a>Fehlerbedingungen

|**Bedingung**|Zurück|**errno**|
|-----------------|------------|-------------|
|*Puffer* ist **NULL**|-1|**EINVAL**|
|*Format* ist **NULL**|-1|**EINVAL**|
|*Anzahl* < = 0|-1|**EINVAL**|
|*SizeOfBuffer* klein (und *Anzahl* ! = **_TRUNCATE**)|-1 (und *Puffer* auf eine leere Zeichenfolge festgelegt)|**ERANGE**|

## <a name="remarks"></a>Hinweise

Jede dieser Funktionen verwendet einen Zeiger auf eine Argumentliste und formatiert und schreibt bis zu *Anzahl* Zeichen der angegebenen Daten in den Speicher verweist *Puffer* und fügt ein abschließendes Nullzeichen.

Wenn *Anzahl* ist [_TRUNCATE](../../c-runtime-library/truncate.md), und klicken Sie dann diese Funktionen größtmöglicher Teil der Zeichenfolge schreiben passt, *Puffer* lassen Platz für ein abschließendes Nullzeichen. Wenn die gesamte Zeichenfolge (mit dem abschließenden Nullzeichen) in passt *Puffer*, klicken Sie dann diese Funktionen die Anzahl der (ohne das abschließende Nullzeichen) geschriebenen Zeichen zurück; andernfalls geben diese Funktionen – 1, um anzugeben, dass Daten abgeschnitten zurück ist aufgetreten.

Die Versionen dieser Funktionen mit dem **_l** -Suffix sind beinahe identisch, verwenden jedoch den Gebietsschemaparameter, der übergebenen Gebietsschemaparameter anstelle des aktuellen threadgebietsschemas.

> [!IMPORTANT]
> Stellen Sie sicher, dass *format* keine benutzerdefinierte Zeichenfolge ist. Weitere Informationen finden Sie unter [Vermeiden von Pufferüberläufen](http://msdn.microsoft.com/library/windows/desktop/ms717795).

> [!NOTE]
> Um sicherzustellen, dass genügend Platz für das abschließende Nullzeichen vorhanden ist, achten Sie darauf, *Anzahl* ist kleiner als die Pufferlänge ist oder die Verwendung **_TRUNCATE**.

In C++ wird die Verwendung dieser Funktionen durch Vorlagenüberladungen vereinfacht; die Überladungen können automatisch Rückschlüsse auf die Pufferlänge ziehen (wodurch kein Größenargument mehr angegeben werden muss), und sie können automatisch die älteren, nicht sicheren Funktionen durch ihre neueren, sicheren Entsprechungen ersetzen. Weitere Informationen finden Sie unter [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md).

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_vsntprintf_s**|**_vsnprintf_s**|**_vsnprintf_s**|**_vsnwprintf_s**|
|**_vsntprintf_s_l**|**_vsnprintf_s_l**|**_vsnprintf_s_l**|**_vsnwprintf_s_l**|

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|Optionale Header|
|-------------|---------------------|----------------------|
|**vsnprintf_s**|\<stdio.h> und \<stdarg.h>|\<varargs.h>*|
|**_vsnprintf_s**, **_vsnprintf_s_l**|\<stdio.h> und \<stdarg.h>|\<varargs.h>*|
|**_vsnwprintf_s**, **_vsnwprintf_s_l**|\<stdio.h> oder \<wchar.h> und \<stdarg.h>|\<varargs.h>*|

\* Benötigt für die Kompatibilität mit UNIX V.

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```cpp
// crt_vsnprintf_s.cpp
#include <stdio.h>
#include <wtypes.h>

void FormatOutput(LPCSTR formatstring, ...)
{
   int nSize = 0;
   char buff[10];
   memset(buff, 0, sizeof(buff));
   va_list args;
   va_start(args, formatstring);
   nSize = vsnprintf_s( buff, _countof(buff), _TRUNCATE, formatstring, args);
   printf("nSize: %d, buff: %s\n", nSize, buff);
   va_end(args);
}

int main() {
   FormatOutput("%s %s", "Hi", "there");
   FormatOutput("%s %s", "Hi", "there!");
   FormatOutput("%s %s", "Hi", "there!!");
}
```

```Output
nSize: 8, buff: Hi there
nSize: 9, buff: Hi there!
nSize: -1, buff: Hi there!
```

## <a name="see-also"></a>Siehe auch

[Stream-E/A](../../c-runtime-library/stream-i-o.md)<br/>
[vprintf-Funktionen](../../c-runtime-library/vprintf-functions.md)<br/>
[fprintf, _fprintf_l, fwprintf, _fwprintf_l](fprintf-fprintf-l-fwprintf-fwprintf-l.md)<br/>
[printf, _printf_l, wprintf, _wprintf_l](printf-printf-l-wprintf-wprintf-l.md)<br/>
[sprintf, _sprintf_l, swprintf, _swprintf_l, \__swprintf_l](sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)<br/>
[va_arg, va_copy, va_end, va_start](va-arg-va-copy-va-end-va-start.md)<br/>
