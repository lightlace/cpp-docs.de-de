---
title: _itoa _itow Funktionen | Microsoft Docs
ms.custom: ''
ms.date: 03/21/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- itoa
- _itoa
- ltoa
- _ltoa
- ultoa
- _ultoa
- _i64toa
- _ui64toa
- _itow
- _ltow
- _ultow
- _i64tow
- _ui64tow
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
- api-ms-win-crt-convert-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _itoa
- _ltoa
- _ultoa
- _i64toa
- _ui64toa
- _itow
- _ltow
- _ultow
- _i64tow
- _ui64tow
- itoa
- ltoa
- ultoa
- i64toa
- ui64toa
- itow
- ltow
- ultow
- i64tow
- ui64tow
- itot
- _itot
- ltot
- _ltot
- ultot
- _ultot
- i64tot
- _i64tot
- ui64tot
- _ui64tot
- _MAX_ITOSTR_BASE16_COUNT
- _MAX_ITOSTR_BASE10_COUNT
- _MAX_ITOSTR_BASE8_COUNT
- _MAX_ITOSTR_BASE2_COUNT
- _MAX_LTOSTR_BASE16_COUNT
- _MAX_LTOSTR_BASE10_COUNT
- _MAX_LTOSTR_BASE8_COUNT
- _MAX_LTOSTR_BASE2_COUNT
- _MAX_ULTOSTR_BASE16_COUNT
- _MAX_ULTOSTR_BASE10_COUNT
- _MAX_ULTOSTR_BASE8_COUNT
- _MAX_ULTOSTR_BASE2_COUNT
- _MAX_I64TOSTR_BASE16_COUNT
- _MAX_I64TOSTR_BASE10_COUNT
- _MAX_I64TOSTR_BASE8_COUNT
- _MAX_I64TOSTR_BASE2_COUNT
- _MAX_U64TOSTR_BASE16_COUNT
- _MAX_U64TOSTR_BASE10_COUNT
- _MAX_U64TOSTR_BASE8_COUNT
- _MAX_U64TOSTR_BASE2_COUNT
dev_langs:
- C++
helpviewer_keywords:
- _itot function
- ui64toa function
- _ui64toa function
- converting integers
- itot function
- _i64tow function
- _i64toa function
- _itow function
- ui64tow function
- integers, converting
- itoa function
- _ui64tow function
- i64tow function
- itow function
- i64toa function
- converting numbers, to strings
- _itoa function
ms.assetid: 46592a00-77bb-4e73-98c0-bf629d96cea6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 95aa140eae6d8a06eff84d03cbb562444c3bd552
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="itoa-itoa-ltoa-ltoa-ultoa-ultoa-i64toa-ui64toa-itow-ltow-ultow-i64tow-ui64tow"></a>Itoa, _itoa, Ltoa, _ltoa, Ultoa, _ultoa, _i64toa, _ui64toa, _itow, _ltow, _ultow _i64tow, _ui64tow

Konvertiert eine ganze Zahl in eine Zeichenfolge. Sicherere Versionen dieser Funktionen sind verfügbar. finden Sie unter [_itoa_s _itow_s Funktionen](itoa-s-itow-s.md).

## <a name="syntax"></a>Syntax

```C
char * _itoa( int value, char *buffer, int radix );
char * _ltoa( long value, char *buffer, int radix );
char * _ultoa( unsigned long value, char *buffer, int radix );
char * _i64toa( long long value, char *buffer, int radix );
char * _ui64toa( unsigned long long value, char *buffer, int radix );

wchar_t * _itow( int value, wchar_t *buffer, int radix );
wchar_t * _ltow( long value, wchar_t *buffer, int radix );
wchar_t * _ultow( unsigned long value, wchar_t *buffer, int radix );
wchar_t * _i64tow( long long value, wchar_t *buffer, int radix );
wchar_t * _ui64tow( unsigned long long value, wchar_t *buffer, int radix );

// These Posix versions of the functions have deprecated names:
char * itoa( int value, char *buffer, int radix );
char * ltoa( long value, char *buffer, int radix );
char * ultoa( unsigned long value, char *buffer, int radix );

// The following template functions are C++ only:
template <size_t size>
char *_itoa( int value, char (&buffer)[size], int radix );

template <size_t size>
char *_itoa( long value, char (&buffer)[size], int radix );

template <size_t size>
char *_itoa( unsigned long value, char (&buffer)[size], int radix );

template <size_t size>
char *_i64toa( long long value, char (&buffer)[size], int radix );

template <size_t size>
char * _ui64toa( unsigned long long value, char (&buffer)[size], int radix );

template <size_t size>
wchar_t * _itow( int value, wchar_t (&buffer)[size], int radix );

template <size_t size>
wchar_t * _ltow( long value, wchar_t (&buffer)[size], int radix );

template <size_t size>
wchar_t * _ultow( unsigned long value, wchar_t (&buffer)[size], int radix );

template <size_t size>
wchar_t * _i64tow( long long value, wchar_t (&buffer)[size], int radix );

template <size_t size>
wchar_t * _ui64tow( unsigned long long value, wchar_t (&buffer)[size],
   int radix );
```

### <a name="parameters"></a>Parameter

*Wert*<br/>
Zu konvertierende Zahl.

*buffer*<br/>
Der Puffer, der das Ergebnis der Konvertierung enthält.

*radix*<br/>
Die Basis, die für die Konvertierung des verwendet *Wert*, die im Bereich 2 – 36 sein muss.

*size*<br/>
Die Länge des Puffers in Einheiten, der den Zeichentyp. Dieser Parameter wird abgeleitet aus dem *Puffer* Argument in C++.

## <a name="return-value"></a>Rückgabewert

Jede dieser Funktionen gibt einen Zeiger auf *Puffer*. Es gibt keine Fehlerrückgabe.

## <a name="remarks"></a>Hinweise

Die **_itoa**, **_ltoa**, **_ultoa**, **_i64toa**, und **_ui64toa** Funktionen konvertieren die Ziffern des Der angegebene *Wert* Argument auf einen Null-terminierte Zeichenfolge und speichern das Ergebnis (bis zu 33 Zeichen für **_itoa**, **_ltoa**, und  **_ultoa**, und 65 für **_i64toa** und **_ui64toa**) in *Puffer*. Wenn *Basis* gleich 10 und *Wert* ist negativ ist, wird das erste Zeichen von der gespeicherten Zeichenfolge das Minuszeichen (**-**). Die **_itow**, **_ltow**, **_ultow**, **_i64tow**, und **_ui64tow** Funktionen sind Breitzeichen- Versionen von **_itoa**, **_ltoa**, **_ultoa**, **_i64toa**, und **_ui64toa**, bzw.

> [!IMPORTANT]
> Diese Funktionen können nach dem Ende eines Puffers schreiben, die zu klein ist. Um Pufferüberläufe zu verhindern, sicher, dass *Puffer* ist groß genug für die konvertierten Ziffern, das abschließende Null-Zeichen sowie ein Zeichen sein. Missbrauch dieser Funktionen kann schwerwiegende Sicherheitsprobleme in Ihrem Code führen.

Aufgrund ihrer potenzielle Sicherheitsprobleme standardmäßig führen diese Funktionen veraltungswarnung [C4996](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md): **diese Funktion oder Variable unsicher sein. Erwägen Sie** *Safe_function* **stattdessen. Zum Deaktivieren der veraltungswarnung verwenden Sie "_crt_secure_no_warnings".** Es wird empfohlen, Sie ändern den Quellcode mithilfe der *Safe_function* vorgeschlagene Warnmeldung angezeigt wird. Die sichereren Funktionen schreiben nicht mehr Zeichen als die angegebene Puffergröße. Weitere Informationen finden Sie unter [_itoa_s _itow_s Funktionen](itoa-s-itow-s.md).

Für die Verwendung dieser Funktionen ohne die veraltungswarnung definieren die **"_crt_secure_no_warnings"** Präprozessormakro vor dem Einfügen von CRT-Header. Hierzu können Sie in der Befehlszeile an einer Eingabeaufforderung für Entwickler durch Hinzufügen der **/D_CRT_SECURE_NO_WARNINGS** Compileroption, um die **cl** Befehl. Definieren Sie andernfalls das Makro in den Quellcodedateien. Bei Verwendung von vorkompilierten Headern definiert das Makro am oberen Rand des vorkompilierten Headers include-Datei, in der Regel "stdafx.h". Verwenden Sie zum Definieren von Makros in Ihrem Quellcode einer **#define** Richtlinie, bevor Sie alle CRT-Header, wie im folgenden Beispiel einfügen:

```C
#define _CRT_SECURE_NO_WARNINGS 1
#include <stdlib.h>
```

In C++ haben diese Funktionen vorlagenüberladungen, mit die ihre sichereren Entsprechungen aufgerufen. Weitere Informationen finden Sie unter [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md).

Die Posix-Namen **Itoa**, **Ltoa**, und **Ultoa** vorhanden sind, als Aliase für die **_itoa**, **_ltoa**, und **_ultoa** Funktionen. Die Posix-Namen sind veraltet, da sie nicht die Implementierung-spezifische Funktion Dateinamenskonventionen von ISO C. folgen Standardmäßig verursachen diese Funktionen veraltungswarnung [C4996](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md): **der POSIX-Namen für dieses Element ist veraltet. Verwenden Sie stattdessen die ISO C- und C++-konformen Namen:** *New_name*. Es wird empfohlen, Sie ändern den Quellcode Verwendung sichereren Versionen dieser Funktionen **_itoa_s**, **_ltoa_s**, oder **_ultoa_s**. Weitere Informationen finden Sie unter [_itoa_s _itow_s Funktionen](itoa-s-itow-s.md).

Für die Quelle Codeportabilität empfiehlt es sich die Posix-Namen im Code beibehalten werden sollen. Für die Verwendung dieser Funktionen ohne das veraltungswarnung definieren sowohl die **_CRT_NONSTDC_NO_WARNINGS** und **"_crt_secure_no_warnings"** Präprozessormakros vor dem Einfügen von CRT-Header. Hierzu können Sie in der Befehlszeile an einer Eingabeaufforderung für Entwickler durch Hinzufügen der **/D_CRT_SECURE_NO_WARNINGS** und **/D_CRT_NONSTDC_NO_WARNINGS** Optionen für Compiler, die **cl**Befehl. Definieren Sie andernfalls die Makros in den Quellcodedateien. Wenn Sie vorkompilierte Header verwenden, definieren die Makros am oberen Rand des vorkompilierten Headers include-Datei, in der Regel "stdafx.h". Verwenden Sie zum Definieren von Makros in Ihrem Quellcode **#define** Direktiven, bevor Sie alle CRT-Header, wie im folgenden Beispiel einfügen:

```C
#define _CRT_NONSTDC_NO_WARNINGS 1
#define _CRT_SECURE_NO_WARNINGS 1
#include <stdlib.h>
```

### <a name="maximum-conversion-count-macros"></a>Maximale Anzahl konvertierungsmakros

Zum sicheren Puffer für Konvertierungen erstellen, enthält die CRT einige praktische Makros. Diese definieren die Größe des Puffers erforderlich, um den längsten möglichen Wert der jeden ganzzahligen Typs, einschließlich null-Abschlusszeichen konvertiert und Zeichen, für verschiedene allgemeine Basen anmelden. Um sicherzustellen, dass die Konvertierung Puffer groß genug ist, erhalten Sie für jede Konvertierung in die Basis ist *Basis*, verwenden Sie eines der folgenden Makros definiert, wenn Sie den Puffer zuzuweisen. Dadurch werden Puffer Überlauffehler verhindert, wenn ganzzahlige Datentypen in Zeichenfolgen zu konvertieren. Diese Makros sind definiert, wenn Sie in Ihrer Quelle stdlib.h oder wchar.h einschließen.

Um eine der folgenden Makros in eine Zeichenfolgenkonvertierungsfunktion verwenden, deklarieren des Konvertierung Puffers mit der entsprechenden Datentyp und den Makrowert für den Integertyp und die Basis als Puffer Dimension. Diese Tabelle enthält die Makros, die für jede Funktion für den aufgelisteten Basen geeignet sind:

||||
|-|-|-|
|Funktionen|radix|Makros|
|**_itoa**, **_itow**|16<br/>10<br/>8<br/>2|**_MAX_ITOSTR_BASE16_COUNT**<br/>**_MAX_ITOSTR_BASE10_COUNT**<br/>**_MAX_ITOSTR_BASE8_COUNT**<br/>**_MAX_ITOSTR_BASE2_COUNT**|
|**_ltoa**, **_ltow**|16<br/>10<br/>8<br/>2|**_MAX_LTOSTR_BASE16_COUNT**<br/>**_MAX_LTOSTR_BASE10_COUNT**<br/>**_MAX_LTOSTR_BASE8_COUNT**<br/>**_MAX_LTOSTR_BASE2_COUNT**|
|**_ultoa**, **_ultow**|16<br/>10<br/>8<br/>2|**_MAX_ULTOSTR_BASE16_COUNT**<br/>**_MAX_ULTOSTR_BASE10_COUNT**<br/>**_MAX_ULTOSTR_BASE8_COUNT**<br/>**_MAX_ULTOSTR_BASE2_COUNT**|
|**_i64toa**, **_i64tow**|16<br/>10<br/>8<br/>2|**_MAX_I64TOSTR_BASE16_COUNT**<br/>**_MAX_I64TOSTR_BASE10_COUNT**<br/>**_MAX_I64TOSTR_BASE8_COUNT**<br/>**_MAX_I64TOSTR_BASE2_COUNT**|
|**_ui64toa**, **_ui64tow**|16<br/>10<br/>8<br/>2|**_MAX_U64TOSTR_BASE16_COUNT**<br/>**_MAX_U64TOSTR_BASE10_COUNT**<br/>**_MAX_U64TOSTR_BASE8_COUNT**<br/>**_MAX_U64TOSTR_BASE2_COUNT**|

In diesem Beispiel verwendet eine Konvertierung Count-Makro definieren Sie einen Puffer groß genug für eine **unsigned long long** im Basis-2:

```cpp
#include <wchar.h>
#include <iostream>
int main()
{
    wchar_t buffer[_MAX_U64TOSTR_BASE2_COUNT];
    std:wcout << _ui64tow(0xFFFFFFFFFFFFFFFFull, buffer, 2) << std::endl;
}
```

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|Tchar.h-Routine|_UNICODE und _MBCS nicht definiert|_MBCS definiert|_UNICODE definiert|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_itot**|**_itoa**|**_itoa**|**_itow**|
|**_ltot**|**_ltoa**|**_ltoa**|**_ltow**|
|**_ultot**|**_ultoa**|**_ultoa**|**_ultow**|
|**_i64tot**|**_i64toa**|**_i64toa**|**_i64tow**|
|**_ui64tot**|**_ui64toa**|**_ui64toa**|**_ui64tow**|

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|
|-------------|---------------------|
|**Itoa**, **Ltoa**, **Ultoa**|\<stdlib.h>|
|**_itoa**, **_ltoa**, **_ultoa**, **_i64toa**, **_ui64toa**|\<stdlib.h>|
|**_itow**, **_ltow**, **_ultow**, **_i64tow**, **_ui64tow**|\<stdlib.h> oder \<wchar.h>|

Diese Funktionen und Makros sind Microsoft-spezifisch. Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

Dieses Beispiel veranschaulicht die Verwendung einiger der Konvertierungsfunktionen ganze Zahl. Beachten Sie die Verwendung der **"_crt_secure_no_warnings"** -Makro Warnung C4996 zu unterdrücken.

```C
// crt_itoa.c
// Compile by using: cl /W4 crt_itoa.c
// This program makes use of the _itoa functions
// in various examples.

#define _CRT_SECURE_NO_WARNINGS 1
#include <stdio.h>      // for printf
#include <string.h>     // for strnlen
#include <stdlib.h>     // for _countof, _itoa fns, _MAX_COUNT macros

int main(void)
{
    char buffer[_MAX_U64TOSTR_BASE2_COUNT];
    int r;

    for (r = 10; r >= 2; --r)
    {
        _itoa(-1, buffer, r);
        printf("base %d: %s (%d chars)\n", r, buffer,
            strnlen(buffer, _countof(buffer)));
    }
    printf("\n");

    for (r = 10; r >= 2; --r)
    {
        _i64toa(-1LL, buffer, r);
        printf("base %d: %s (%d chars)\n", r, buffer,
            strnlen(buffer, _countof(buffer)));
    }
    printf("\n");

    for (r = 10; r >= 2; --r)
    {
        _ui64toa(0xffffffffffffffffULL, buffer, r);
        printf("base %d: %s (%d chars)\n", r, buffer,
            strnlen(buffer, _countof(buffer)));
    }
}
```

```Output
base 10: -1 (2 chars)
base 9: 12068657453 (11 chars)
base 8: 37777777777 (11 chars)
base 7: 211301422353 (12 chars)
base 6: 1550104015503 (13 chars)
base 5: 32244002423140 (14 chars)
base 4: 3333333333333333 (16 chars)
base 3: 102002022201221111210 (21 chars)
base 2: 11111111111111111111111111111111 (32 chars)

base 10: -1 (2 chars)
base 9: 145808576354216723756 (21 chars)
base 8: 1777777777777777777777 (22 chars)
base 7: 45012021522523134134601 (23 chars)
base 6: 3520522010102100444244423 (25 chars)
base 5: 2214220303114400424121122430 (28 chars)
base 4: 33333333333333333333333333333333 (32 chars)
base 3: 11112220022122120101211020120210210211220 (41 chars)
base 2: 1111111111111111111111111111111111111111111111111111111111111111 (64 chars)

base 10: 18446744073709551615 (20 chars)
base 9: 145808576354216723756 (21 chars)
base 8: 1777777777777777777777 (22 chars)
base 7: 45012021522523134134601 (23 chars)
base 6: 3520522010102100444244423 (25 chars)
base 5: 2214220303114400424121122430 (28 chars)
base 4: 33333333333333333333333333333333 (32 chars)
base 3: 11112220022122120101211020120210210211220 (41 chars)
base 2: 1111111111111111111111111111111111111111111111111111111111111111 (64 chars)
```

## <a name="see-also"></a>Siehe auch

[Datenkonvertierung](../../c-runtime-library/data-conversion.md)<br/>
[_itoa_s _itow_s-Funktionen](itoa-s-itow-s.md)<br/>
