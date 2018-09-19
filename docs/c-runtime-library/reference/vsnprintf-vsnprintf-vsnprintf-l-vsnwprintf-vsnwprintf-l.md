---
title: vsnprintf, _vsnprintf, _vsnprintf_l, _vsnwprintf, _vsnwprintf_l | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _vsnprintf
- _vsnprintf_l
- _vsnwprintf
- _vsnwprintf_l
- _vsnprintf
- _vsnprintf;
- vsnprintf; _vsnprintf
- _vsnwprintf;
- _vsnprintf_l;
- _vsnwprintf_l;
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
- ntoskrnl.exe
- ucrtbase.dll
apitype: DLLExport
f1_keywords:
- _vsnprintf
- _vsnwprintf
- _vsntprintf
- vsnprintf
- stdio/vsnprintf
- stdio/_vsnprintf
- stdio/_vsnprintf_l
- stdio/_vsnwprintf
- stdio/_vsnwprintf_l
- _vsnprintf_l
- _vsnwprintf_l
dev_langs:
- C++
helpviewer_keywords:
- vsntprintf function
- _vsnwprintf_l function
- vsnwprintf_l function
- vsntprintf_l function
- _vsntprintf function
- _vsnprintf_l function
- vsnprintf function
- _vsntprintf_l function
- vsnprintf_l function
- _vsnwprintf function
- _vsnprintf function
- formatted text [C++]
- vsnwprintf function
ms.assetid: a97f92df-c2f8-4ea0-9269-76920d2d566a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e5166ef52f88e714d1168fe25a1ec29dd5360205
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43210504"
---
# <a name="vsnprintf-vsnprintf-vsnprintfl-vsnwprintf-vsnwprintfl"></a>vsnprintf, _vsnprintf, _vsnprintf_l, _vsnwprintf, _vsnwprintf_l

Schreiben von formatierter Ausgabe mithilfe eines Zeigers, der auf eine Liste von Argumenten zeigt. Sicherere Versionen dieser Funktionen sind verfügbar. Informationen dazu finden Sie unter [vsnprintf_s, _vsnprintf_s, _vsnprintf_s_l, _vsnwprintf_s, _vsnwprintf_s_l](vsnprintf-s-vsnprintf-s-vsnprintf-s-l-vsnwprintf-s-vsnwprintf-s-l.md).

## <a name="syntax"></a>Syntax

```C
int vsnprintf(
   char *buffer,
   size_t count,
   const char *format,
   va_list argptr
);
int _vsnprintf(
   char *buffer,
   size_t count,
   const char *format,
   va_list argptr
);
int _vsnprintf_l(
   char *buffer,
   size_t count,
   const char *format,
   locale_t locale,
   va_list argptr
);
int _vsnwprintf(
   wchar_t *buffer,
   size_t count,
   const wchar_t *format,
   va_list argptr
);
int _vsnwprintf_l(
   wchar_t *buffer,
   size_t count,
   const wchar_t *format,
   locale_t locale,
   va_list argptr
);
template <size_t size>
int vsnprintf(
   char (&buffer)[size],
   size_t count,
   const char *format,
   va_list argptr
); // C++ only
template <size_t size>
int _vsnprintf(
   char (&buffer)[size],
   size_t count,
   const char *format,
   va_list argptr
); // C++ only
template <size_t size>
int _vsnprintf_l(
   char (&buffer)[size],
   size_t count,
   const char *format,
   locale_t locale,
   va_list argptr
); // C++ only
template <size_t size>
int _vsnwprintf(
   wchar_t (&buffer)[size],
   size_t count,
   const wchar_t *format,
   va_list argptr
); // C++ only
template <size_t size>
int _vsnwprintf_l(
   wchar_t (&buffer)[size],
   size_t count,
   const wchar_t *format,
   locale_t locale,
   va_list argptr
); // C++ only
```

### <a name="parameters"></a>Parameter

*buffer*<br/>
Speicherort für die Ausgabe.

*count*<br/>
Maximale Anzahl der zu schreibenden Zeichen.

*format*<br/>
Formatangabe.

*argptr*<br/>
Zeiger zur Liste der Argumente.

*locale*<br/>
Das zu verwendende Gebietsschema.

Weitere Informationen finden Sie unter [Formatangaben](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md).

## <a name="return-value"></a>Rückgabewert

Die **Vsnprintf** Funktion gibt die Anzahl der geschriebenen Zeichen des abschließenden Zeichens Null wird dabei nicht mitgezählt. Wenn die Größe des Puffers angegeben *Anzahl* ist nicht ausreichend groß ist, um die Ausgabe gemäß *Format* und *Argptr*, der Rückgabewert von  **Vsnprintf** ist die Anzahl der Zeichen, die keine Null-Zeichen gezählt, wenn geschrieben werden sollen, *Anzahl* groß genug wäre. Wenn der Rückgabewert größer als *Anzahl* - 1, die Ausgabe wurde abgeschnitten. Der Rückgabewert „-1“ gibt an, dass ein Codierungsfehler aufgetreten ist.

Beide **_vsnprintf** und **_vsnwprintf** Funktionen zurück, die Anzahl von Zeichen geschrieben, wenn die Anzahl der zu schreibenden Zeichen kleiner als oder gleich ist *Anzahl*; Wenn die Zahl der zu schreibenden Zeichen ist größer als *Anzahl*, geben diese Funktionen-1 zurück, der angibt, dass die Ausgabe wurde abgeschnitten.

Der von allen diesen Funktionen zurückgegebene Wert enthält nicht das abschließende Zeichen NULL, unabhängig davon, ob es geschrieben wurde oder nicht. Wenn *Anzahl* 0 (null), ist der zurückgegebene Wert ist die Anzahl der Zeichen, die die Funktionen, nicht schreiben würden einschließlich abschließende Null. Sie können dieses Ergebnis dazu verwenden, ausreichend Pufferspeicher für die Zeichenfolge und dessen abschließendes NULL-Zeichen zuzuordnen, und die Funktion dann erneut aufrufen, um den Puffer zu füllen.

Wenn *Format* ist **NULL**, oder wenn *Puffer* ist **NULL** und *Anzahl* ist nicht gleich NULL, diese Funktionen der Handler für ungültige Parameter aufgerufen, siehe [Parametervalidierung](../../c-runtime-library/parameter-validation.md). Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, geben diese Funktionen-1 zurück und legen Sie **Errno** zu **EINVAL**.

## <a name="remarks"></a>Hinweise

Jede dieser Funktionen verwendet einen Zeiger auf eine Argumentliste und formatiert die Daten und schreibt bis zu *Anzahl* Zeichen in den Speicher verweist *Puffer*. Die **Vsnprintf** -Funktion schreibt immer einen null-Terminator, selbst wenn die Ausgabe abgeschnitten. Bei Verwendung **_vsnprintf** und **_vsnwprintf**, der Puffer wird werden Null-terminierte nur dann, wenn am Ende Platz verfügbar ist (d. h., wenn die Anzahl der zu schreibenden Zeichen kleiner als *Anzahl*).

> [!IMPORTANT]
> Um bestimmte Arten von Sicherheitsrisiken zu verhindern, stellen sicher, dass *Format* ist keine benutzerdefinierte Zeichenfolge. Weitere Informationen finden Sie unter [Vermeiden von Pufferüberläufen](/windows/desktop/SecBP/avoiding-buffer-overruns).

> [!NOTE]
> Um sicherzustellen, dass genügend Platz vorhanden für das abschließende Nullzeichen beim Aufrufen von ist **_vsnprintf**, **_vsnprintf_l**, **_vsnwprintf** und **_vsnwprintf_l**, stellen sicher, dass *Anzahl* strikt kleiner als die Pufferlänge ist, und initialisieren Sie den Puffer vor dem Aufrufen der Funktion NULL.
>
> Da **Vsnprintf** immer schreibt das abschließende Null-Zeichen, die *Anzahl* Parameter kann gleich der Größe des Puffers sein.

Beginnend mit der UCRT in Visual Studio 2015 und Windows 10, **Vsnprintf** ist nicht mehr identisch mit **_vsnprintf**. Die **Vsnprintf** Funktion entspricht dem Standard C99 konform; **_vnsprintf** Gründen der Abwärtskompatibilität mit älterem Visual Studio-Code beibehalten wird.

Die Versionen dieser Funktionen mit den **_l** -Suffix sind beinahe identisch, außer dass sie den übergebenen Gebietsschemaparameter anstelle des aktuellen threadgebietsschemas Locale-Parameter verwenden.

In C++ haben diese Funktionen Vorlagenüberladungen, mit denen die neueren, sicheren Entsprechungen dieser Funktionen aufgerufen werden. Weitere Informationen finden Sie unter [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md).

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_vsntprintf**|**_vsnprintf**|**_vsnprintf**|**_vsnwprintf**|
|**_vsntprintf_l**|**_vsnprintf_l**|**_vsnprintf_l**|**_vsnwprintf_l**|

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header (C)|Erforderlicher Header (C++)|
|-------------|---------------------------|-------------------------------|
|**Vsnprintf**, **_vsnprintf**, **_vsnprintf_l**|\<stdio.h>|\<stdio.h> oder \<cstdio>|
|**_vsnwprintf**, **_vsnwprintf_l**|\<stdio.h> oder \<wchar.h>|\<stdio.h>, \<wchar.h>, \<cstdio> oder \<cwchar>|

Die **_vsnprintf**, **_vsnprintf_l**, **_vsnwprintf** und **_vsnwprintf_l** Funktionen sind Microsoft-spezifisch. Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```C
// crt_vsnwprintf.c
// compile by using: cl /W3 crt_vsnwprintf.c

// To turn off error C4996, define this symbol:
#define _CRT_SECURE_NO_WARNINGS

#include <stdio.h>
#include <wtypes.h>

#define BUFFCOUNT (10)

void FormatOutput(LPCWSTR formatstring, ...)
{
    int nSize = 0;
    wchar_t buff[BUFFCOUNT];
    memset(buff, 0, sizeof(buff));
    va_list args;
    va_start(args, formatstring);
    // Note: _vsnwprintf is deprecated; consider vsnwprintf_s instead
    nSize = _vsnwprintf(buff, BUFFCOUNT - 1, formatstring, args); // C4996
    wprintf(L"nSize: %d, buff: %ls\n", nSize, buff);
    va_end(args);
}

int main() {
    FormatOutput(L"%ls %ls", L"Hi", L"there");
    FormatOutput(L"%ls %ls", L"Hi", L"there!");
    FormatOutput(L"%ls %ls", L"Hi", L"there!!");
}
```

```Output
nSize: 8, buff: Hi there
nSize: 9, buff: Hi there!
nSize: -1, buff: Hi there!
```

Das Verhalten ändert sich, wenn Sie stattdessen „vsnprintf“ zusammen mit Parametern mit schmaler Zeichenfolge verwenden. Die *Anzahl* Parameter kann die gesamte Größe des Puffers sein, und der Rückgabewert ist die Anzahl der Zeichen, die Wenn würde geschrieben wurden *Anzahl* groß genug war:

## <a name="example"></a>Beispiel

```C
// crt_vsnprintf.c
// compile by using: cl /W4 crt_vsnprintf.c
#include <stdio.h>
#include <stdarg.h> // for va_list, va_start
#include <string.h> // for memset

#define BUFFCOUNT (10)

void FormatOutput(char* formatstring, ...)
{
    int nSize = 0;
    char buff[BUFFCOUNT];
    memset(buff, 0, sizeof(buff));
    va_list args;
    va_start(args, formatstring);
    nSize = vsnprintf(buff, sizeof(buff), formatstring, args);
    printf("nSize: %d, buff: %s\n", nSize, buff);
    va_end(args);
}

int main() {
    FormatOutput("%s %s", "Hi", "there");   //  8 chars + null
    FormatOutput("%s %s", "Hi", "there!");  //  9 chars + null
    FormatOutput("%s %s", "Hi", "there!!"); // 10 chars + null
}
```

```Output
nSize: 8, buff: Hi there
nSize: 9, buff: Hi there!
nSize: 10, buff: Hi there!
```

## <a name="see-also"></a>Siehe auch

[Stream-E/A](../../c-runtime-library/stream-i-o.md)<br/>
[vprintf-Funktionen](../../c-runtime-library/vprintf-functions.md)<br/>
[Syntax der Formatangabe: printf- und wprintf-Funktionen](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md)<br/>
[fprintf, _fprintf_l, fwprintf, _fwprintf_l](fprintf-fprintf-l-fwprintf-fwprintf-l.md)<br/>
[printf, _printf_l, wprintf, _wprintf_l](printf-printf-l-wprintf-wprintf-l.md)<br/>
[sprintf, _sprintf_l, swprintf, _swprintf_l, \__swprintf_l](sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)<br/>
[va_arg, va_copy, va_end, va_start](va-arg-va-copy-va-end-va-start.md)<br/>
