---
title: scanf_s, _scanf_s_l, wscanf_s, _wscanf_s_l | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- wscanf_s
- _wscanf_s_l
- scanf_s
- _scanf_s_l
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
apitype: DLLExport
f1_keywords:
- wscanf_s
- _tscanf_s_l
- _wscanf_s_l
- scanf_s
- _tscanf_s
- _scanf_s_l
dev_langs: C++
helpviewer_keywords:
- reading data [C++], from input streams
- buffers [C++], buffer overruns
- _scanf_s_l function
- _wscanf_s_l function
- tscanf_s_l function
- tscanf_s function
- scanf_s function
- data [C++], reading from input stream
- wscanf_s function
- _tscanf_s_l function
- _tscanf_s function
- scanf_s_l function
- formatted data [C++], from input streams
- wscanf_s_l function
- buffers [C++], avoiding overruns
ms.assetid: 42cafcf7-52d6-404a-80e4-b056a7faf2e5
caps.latest.revision: "33"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 7bbd71d42e728a39e0c8c20f9a496832f45d33ac
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="scanfs-scanfsl-wscanfs-wscanfsl"></a>scanf_s, _scanf_s_l, wscanf_s, _wscanf_s_l
Liest formatierte Daten aus dem Standardeingabestream. Diese Versionen von [scanf, _scanf_l, wscanf, _wscanf_l](../../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md) enthalten Sicherheitsverbesserungen, wie unter [Sicherheitsfunktionen in der CRT](../../c-runtime-library/security-features-in-the-crt.md) beschrieben.  
  
## <a name="syntax"></a>Syntax  
  
```  
int scanf_s(  
   const char *format [,  
   argument]...   
);  
int _scanf_s_l(  
   const char *format,  
   locale_t locale [,  
   argument]...   
);  
int wscanf_s(  
   const wchar_t *format [,  
   argument]...   
);  
int _wscanf_s_l(  
   const wchar_t *format,  
   locale_t locale [,  
   argument]...   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `format`  
 Formatsteuerzeichenfolge.  
  
 `argument`  
 Optionale Argumente.  
  
 `locale`  
 Das zu verwendende Gebietsschema.  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt die Anzahl von Feldern zurück, die erfolgreich konvertiert und zugewiesen wurden; der Rückgabewert umfasst keine Felder, die gelesen, aber nicht zugewiesen wurden. Ein Rückgabewert von 0 gibt an, dass keine Felder zugewiesen wurden. Der Rückgabewert ist im Fall eines Fehlers `EOF`. Dies gilt auch, wenn das Dateiendezeichen oder das Zeichenfolgeendezeichen beim ersten Versuch, das Zeichen zu lesen, erkannt wird. Wenn `format` ein `NULL`-Zeiger ist, wird der Handler für ungültige Parameter wie unter [Parameter Validation (Parameterüberprüfung)](../../c-runtime-library/parameter-validation.md) beschrieben aufgerufen. Wenn die weitere Ausführung zugelassen wird, geben `scanf_s` und `wscanf_s` den Wert `EOF` zurück und setzen `errno` auf `EINVAL`.  
  
 Weitere Informationen zu diesen und anderen Fehlercodes finden Sie unter [errno, _doserrno, _sys_errlist, and _sys_nerr (errno, _doserrno, _sys_errlist und _sys_nerr)](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Hinweise  
 Die `scanf_s`-Funktion liest Daten aus dem Standardeingabestream `stdin` und schreibt die Daten in den Speicherort, der von `argument` angegeben wird. Jedes `argument` muss ein Zeiger auf einen Variablentyp sein, der einem Typspezifizierer im `format` entspricht. Wenn der Kopiervorgang zwischen Zeichenfolgen ausgeführt wird, die sich überschneiden, ist das Verhalten nicht definiert.  
  
 `wscanf_s` ist eine Breitzeichenversion von `scanf_s`. Das `format`-Argument für `wscanf_s` ist eine Breitzeichenfolge. `wscanf_s` und `scanf_s` verhalten sich identisch, wenn der Stream in ANSI-Modus geöffnet ist. `scanf_s` unterstützt derzeit nicht die Eingabe aus einem UNICODE-Stream.  
  
 Die Versionen dieser Funktionen mit dem `_l`-Suffix sind beinahe identisch, verwenden jedoch den Gebietsschemaparameter, der anstelle des aktuellen Threadgebietsschemas übergeben wurde.  
  
 Anders als `scanf` und `wscanf` erfordern `scanf_s` und `wscanf_s` eine Angabe der Puffergröße für alle Eingabeparameter vom Typ `c`, `C`, `s` und `S` oder Zeichenfolgensätze, die in `[]` enthalten sind. Die Puffergröße in Zeichen wird als zusätzlicher Parameter direkt nach dem Zeiger auf den Puffer oder die Variable übergeben. Beim Lesen einer Zeichenfolge wird beispielsweise die Puffergröße für diese Zeichenfolge wie folgt übergeben:  
  
 `char s[10];`  
  
 `scanf_s("%9s", s, (unsigned)_countof(s)); // buffer size is 10, width specification is 9`  
  
 Die Puffergröße enthält das abschließende NULL-Zeichen. Sie können ein Feld für die Breitenangabe verwenden, um sicherzustellen, dass das eingelesene Token in den Puffer passt. Wenn kein Feld für die Breiteangabe verwendet wird und das eingelesen Token zu groß für den Puffer ist, wird nichts in diesen Puffer geschrieben.  
  
> [!NOTE]
>  Der Größenparameter ist vom Typ `unsigned` und nicht vom Typ `size_t`. Verwenden Sie eine statistische Umwandlung, um einen `size_t`-Wert in `unsigned` für 64-Bit-Buildkonfigurationen zu konvertieren.  
  
 Im folgenden Beispiel wird gezeigt, dass der Puffergrößenparameter die maximale Anzahl von Zeichen, aber nicht von Bytes beschreibt. Im Aufruf von `wscanf_s`, stimmt die Zeichenbreite, die von dem Puffertyp angegeben ist, nicht mit der Zeichenbreite überein, die im Formatbezeichner angegeben ist.  
  
```  
wchar_t ws[10];  
wscanf_s(L"%9S", ws, (unsigned)_countof(ws));  
```  
  
 Der Formatbezeichner `S` gibt die Verwendung der Zeichenbreite an, die zu der von der Funktion unterstützten Standardbreite einen "Gegensatz" darstellt. Die Zeichen sind ein Byte breit, aber die Funktion unterstützt Doppelbytezeichen. In diesem Beispiel wird eine Zeichenfolge bis maximal 9 Einzelbytezeichen eingelesen und an einen Puffer für Doppelbytezeichen übergeben. Die Zeichen werden als Einzelbytewerte behandelt; die ersten zwei Zeichen werden in `ws[0]` gespeichert, die zweiten zwei Zeichen in `ws[1]` usw.  
  
 Im Fall von Zeichen wird ein einzelnes Zeichen wie folgt gelesen:  
  
 `char c;`  
  
 `scanf_s("%c", &c, 1);`  
  
 Wenn mehrere Zeichen für Zeichenfolgen gelesen werden, die nicht mit NULL abschließen, werden ganze Zahlen für die Breitenangabe und die Puffergröße verwendet.  
  
 `char c[4];`  
  
 `scanf_s("%4c", &c, (unsigned)_countof(c)); // not null terminated`  
  
 Weitere Informationen finden Sie unter [scanf-Breitenangabe](../../c-runtime-library/scanf-width-specification.md).  
  
### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen  
  
|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tscanf_s`|`scanf_s`|`scanf_s`|`wscanf_s`|  
|`_tscanf_s_l`|`_scanf_s_l`|`_scanf_s_l`|`_wscanf_s_l`|  
  
 Weitere Informationen finden Sie unter [Format Specification Fields: scanf and wscanf Functions (Formatspezifikationsfelder: Funktionen scanf und wscanf)](../../c-runtime-library/format-specification-fields-scanf-and-wscanf-functions.md).  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------|  
|`scanf_s`, `_scanf_s_l`|\<stdio.h>|  
|`wscanf_s`, `_wscanf_s_l`|\<stdio.h> oder \<wchar.h>|  
  
 Die Konsole wird in [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)]-Apps nicht unterstützt. Die mit der Konsole verknüpften Standardstreamhandles, `stdin`, `stdout` und `stderr`, müssen umgeleitet werden, bevor sie von C-Laufzeitfunktionen in [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)]-Apps verwendet werden können. Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Beispiel  
  
```  
// crt_scanf_s.c  
// This program uses the scanf_s and wscanf_s functions  
// to read formatted input.  
  
#include <stdio.h>  
#include <stdlib.h>  
  
int main( void )  
{  
   int      i,  
            result;  
   float    fp;  
   char     c,  
            s[80];  
   wchar_t  wc,  
            ws[80];  
  
   result = scanf_s( "%d %f %c %C %s %S", &i, &fp, &c, 1,  
                     &wc, 1, s, (unsigned)_countof(s), ws, (unsigned)_countof(ws) );  
   printf( "The number of fields input is %d\n", result );  
   printf( "The contents are: %d %f %c %C %s %S\n", i, fp, c,  
           wc, s, ws);  
   result = wscanf_s( L"%d %f %hc %lc %S %ls", &i, &fp, &c, 2,  
                      &wc, 1, s, (unsigned)_countof(s), ws, (unsigned)_countof(ws) );  
   wprintf( L"The number of fields input is %d\n", result );  
   wprintf( L"The contents are: %d %f %C %c %hs %s\n", i, fp,  
            c, wc, s, ws);  
}  
```  
  
 Dieses Programm generiert bei dieser Eingabe die folgende Ausgabe:  
  
 `71 98.6 h z Byte characters`  
  
 `36 92.3 y n Wide characters`  
  
```Output  
The number of fields input is 6  
The contents are: 71 98.599998 h z Byte characters  
The number of fields input is 6  
The contents are: 36 92.300003 y n Wide characters  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Floating-Point Support (Gleitkommaunterstützung)](../../c-runtime-library/floating-point-support.md)   
 [Stream I/O (Stream-E/A)](../../c-runtime-library/stream-i-o.md)   
 [Locale](../../c-runtime-library/locale.md)   
 [fscanf, _fscanf_l, fwscanf, _fwscanf_l](../../c-runtime-library/reference/fscanf-fscanf-l-fwscanf-fwscanf-l.md)   
 [printf, _printf_l, wprintf, _wprintf_l](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)   
 [sprintf, _sprintf_l, swprintf, _swprintf_l, \__swprintf_l](../../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)   
 [sscanf, _sscanf_l, swscanf, _swscanf_l](../../c-runtime-library/reference/sscanf-sscanf-l-swscanf-swscanf-l.md)