---
title: strtok, _strtok_l, wcstok, _wcstok_l, _mbstok, _mbstok_l | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _mbstok_l
- _mbstok
- wcstok
- _mbstok
- strtok
- _wcstok_l
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
- api-ms-win-crt-string-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _mbstok
- strtok
- _tcstok
- wcstok
dev_langs:
- C++
helpviewer_keywords:
- mbstok_l function
- strings [C++], searching
- tcstok function
- _tcstok function
- _strtok_l function
- strtok function
- mbstok function
- wcstok_l function
- _mbstok function
- tcstok_l function
- tokens, finding in strings
- _mbstok_l function
- wcstok function
- _wcstok_l function
- _tcstok_l function
- strtok_l function
ms.assetid: 904cb734-f0d7-4d77-ba81-4791ddf461ae
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 45e2155f830a302f316aa96ce41b65a71709bc0d
ms.sourcegitcommit: 6e3cf8df676d59119ce88bf5321d063cf479108c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/22/2018
ms.locfileid: "34451796"
---
# <a name="strtok-strtokl-wcstok-wcstokl-mbstok-mbstokl"></a>strtok, _strtok_l, wcstok, _wcstok_l, _mbstok, _mbstok_l

Sucht das nächste Token in einer Zeichenfolge unter Verwendung des angegebenen Gebietsschemas oder eines Gebietsschemas, das übergeben wird. Sicherere Versionen dieser Funktionen sind verfügbar. Informationen dazu finden Sie unter [strtok_s, _strtok_s_l, wcstok_s, _wcstok_s_l, _mbstok_s, _mbstok_s_l](strtok-s-strtok-s-l-wcstok-s-wcstok-s-l-mbstok-s-mbstok-s-l.md).

> [!IMPORTANT]
> **_mbstok** und **_mbstok_l** kann nicht in Anwendungen, die in der Windows-Runtime ausgeführt verwendet werden. Weitere Informationen finden Sie im Artikel [CRT functions not supported in Universal Windows Platform apps (In Apps für die universelle Windows-Plattform nicht unterstützte CRT-Funktionen)](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Syntax

```C
char *strtok(
   char *strToken,
   const char *strDelimit
);
wchar_t *wcstok(
   wchar_t *strToken,
   const wchar_t *strDelimit
);
unsigned char *_mbstok(
   unsigned char*strToken,
   const unsigned char *strDelimit
);
unsigned char *_mbstok(
   unsigned char*strToken,
   const unsigned char *strDelimit,
   _locale_t locale
);
```

### <a name="parameters"></a>Parameter

*strToken*<br/>
Zeichenfolge, die mindestens ein Token enthält.

*strDelimit*<br/>
Gruppe von Trennzeichen.

*locale*<br/>
Zu verwendendes Gebietsschema.

## <a name="return-value"></a>Rückgabewert

Gibt einen Zeiger auf das nächste Token in gefunden *StrToken*. Diese zurückgeben **NULL** Wenn keine weiteren Token gefunden werden. Jeder Aufruf ändert *StrToken* durch das Ersetzen von Trennzeichen, das nach dem zurückgegebenen Token auftritt, ein Null-Zeichen.

## <a name="remarks"></a>Hinweise

Die **Strtok** -Funktion sucht das nächste Token in *StrToken*. Der Satz von Zeichen im *StrDelimit* gibt mögliche Trennzeichen des Tokens in gefunden werden *StrToken* für den aktuellen Aufruf. **Wcstok** und **_mbstok** sind Breitzeichen- und multibytezeichenversionen von **Strtok**. Die Argumente und der Rückgabewert von **Wcstok** sind Breitzeichen-Zeichenfolgen, die von **_mbstok** sind Multibyte Zeichenfolgen. Diese drei Funktionen verhalten sich andernfalls identisch.

> [!IMPORTANT]
> Diese Funktionen stellen eine mögliche Bedrohung aufgrund eines Pufferüberlaufproblems dar. Pufferüberlaufprobleme werden häufig bei Systemangriffen eingesetzt, da sie zu einer unbefugten Ausweitung der Berechtigungen führen. Weitere Informationen finden Sie unter [Vermeiden von Pufferüberläufen](http://msdn.microsoft.com/library/windows/desktop/ms717795).

Beim ersten Aufruf von **Strtok**, die Funktion vorangestellte Trennzeichen überspringt und gibt einen Zeiger auf das erste Token in *StrToken*, beendet das Token mit einem Null-Zeichen. Weitere Token können der Rest des geholt werden *StrToken* durch eine Reihe von Aufrufen an **Strtok**. Jeder Aufruf von **Strtok** ändert *StrToken* durch ein Null-Zeichen nach dem Einfügen der **token** zurückgegebenen. Lesen Sie das nächste Token von *StrToken*, rufen Sie **Strtok** mit einer **NULL** Wert für die *StrToken* Argument. Die **NULL** *StrToken* Argument bewirkt, dass **Strtok** , suchen Sie nach dem nächsten Token im geänderten *StrToken*. Die *StrDelimit* Argument kann jeden beliebigen Wert annehmen zwischen zwei aufrufen zur nächsten, damit der Satz von Trennzeichen variieren kann.

Der Ausgabewert ist von der Kategorieeinstellung **LC_CTYPE** des Gebietsschemas betroffen. Weitere Informationen finden Sie unter [setlocale](setlocale-wsetlocale.md). Die Versionen dieser Funktionen ohne das **_l**-Suffix verwenden das aktuelle Gebietsschema für dieses vom Gebietsschema abhängige Verhalten; die Versionen mit dem **_l**-Suffix sind beinahe identisch, verwenden jedoch stattdessen den ihnen übergebenen Gebietsschemaparameter. Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).

> [!NOTE]
> Jede Funktion verwendet eine statische Variable eines lokalen Threads, um die Zeichenfolge in Token zu analysieren. Daher können mehrere Threads diese Funktionen gleichzeitig aufrufen, ohne dass unerwünschte Auswirkungen auftreten. Innerhalb eines einzelnen Threads ist es jedoch wahrscheinlich, dass ein überlappendes Aufrufen von einer dieser Funktionen zu Datenbeschädigung und ungenauen Ergebnissen führt. Beim Analysieren verschiedener Zeichenfolgen sollte zuerst eine Zeichenfolge zu Ende analysiert werden, bevor mit dem Analysieren der nächsten Zeichenfolge begonnen wird. Berücksichtigen Sie auch das mögliche Risiko, wenn Sie eine dieser Funktionen aus einer Schleife heraus aufrufen, in der eine andere Funktion aufgerufen wird. Wenn die andere Funktion eine dieser Funktionen verwendet, kommt es zu einer überlappenden Sequenz von Aufrufen und Datenbeschädigung ist die Folge.

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcstok**|**strtok**|**_mbstok**|**wcstok**|
|**_tcstok**|**_strtok_l**|**_mbstok_l**|**_wcstok_l**|

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|
|-------------|---------------------|
|**strtok**|\<string.h>|
|**wcstok**|\<string.h> oder \<wchar.h>|
|**_mbstok**, **_mbstok_l**|\<mbstring.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```C
// crt_strtok.c
// compile with: /W3
// In this program, a loop uses strtok
// to print all the tokens (separated by commas
// or blanks) in the string named "string".
//
#include <string.h>
#include <stdio.h>

char string[] = "A string\tof ,,tokens\nand some  more tokens";
char seps[]   = " ,\t\n";
char *token;

int main( void )
{
   printf( "Tokens:\n" );

   // Establish string and get the first token:
   token = strtok( string, seps ); // C4996
   // Note: strtok is deprecated; consider using strtok_s instead
   while( token != NULL )
   {
      // While there are tokens in "string"
      printf( " %s\n", token );

      // Get next token:
      token = strtok( NULL, seps ); // C4996
   }
}
```

```Output
Tokens:
A
string
of
tokens
and
some
more
tokens
```

## <a name="see-also"></a>Siehe auch

[Zeichenfolgenbearbeitung](../../c-runtime-library/string-manipulation-crt.md)<br/>
[Locale](../../c-runtime-library/locale.md)<br/>
[Interpretation von Multibyte-Zeichensequenzen](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[strcspn, wcscspn, _mbscspn, _mbscspn_l](strcspn-wcscspn-mbscspn-mbscspn-l.md)<br/>
[strspn, wcsspn, _mbsspn, _mbsspn_l](strspn-wcsspn-mbsspn-mbsspn-l.md)<br/>
