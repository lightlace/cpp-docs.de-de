---
title: sscanf_s, _sscanf_s_l, swscanf_s, _swscanf_s_l | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _sscanf_s_l
- sscanf_s
- _swscanf_s_l
- swscanf_s
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
- _stscanf_s
- sscanf_s
- swscanf_s
- _swscanf_s_l
- _stscanf_s_l
- _sscanf_s_l
dev_langs:
- C++
helpviewer_keywords:
- stscanf_s_l function
- stscanf_s function
- swscanf_s function
- swscanf_s_l function
- sscanf_s_l function
- _stscanf_s_l function
- strings [C++], reading data from
- sscanf_s function
- _swscanf_s_l function
- _stscanf_s function
- reading data, strings
- strings [C++], reading
- _sscanf_s_l function
ms.assetid: 956e65c8-00a5-43e8-a2f2-0f547ac9e56c
caps.latest.revision: 30
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: 59693a41b76eb7d6d7bae4c50fa320d8f48c78d1
ms.contentlocale: de-de
ms.lasthandoff: 03/29/2017

---
# <a name="sscanfs-sscanfsl-swscanfs-swscanfsl"></a>sscanf_s, _sscanf_s_l, swscanf_s, _swscanf_s_l
Liest formatierte Daten aus einer Zeichenfolge. Diese Versionen von [sscanf, _sscanf_l, swscanf, _swscanf_l](../../c-runtime-library/reference/sscanf-sscanf-l-swscanf-swscanf-l.md) enthalten Sicherheitsverbesserungen wie unter [Sicherheitsfunktionen in der CRT](../../c-runtime-library/security-features-in-the-crt.md) beschrieben.  
  
## <a name="syntax"></a>Syntax  
  
```  
int sscanf_s(  
   const char *buffer,  
   const char *format [,  
   argument ] ...  
);  
int _sscanf_s_l(  
   const char *buffer,  
   const char *format,  
   locale_t locale [,  
   argument ] ...  
);  
int swscanf_s(  
   const wchar_t *buffer,  
   const wchar_t *format [,  
   argument ] ...  
);  
int _swscanf_s_l(  
   const wchar_t *buffer,  
   const wchar_t *format,  
   locale_t locale [,  
   argument ] ...  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `buffer`  
 Gespeicherte Daten  
  
 `format`  
 Formatsteuerzeichenfolge. Weitere Informationen finden Sie unter [Formatangabefelder: scanf- und wscanf-Funktionen](../../c-runtime-library/format-specification-fields-scanf-and-wscanf-functions.md).  
  
 `argument`  
 Optionale Argumente  
  
 `locale`  
 Das zu verwendende Gebietsschema  
  
## <a name="return-value"></a>Rückgabewert  
 Jede dieser Funktionen gibt die Anzahl der Felder zurück, die erfolgreich konvertiert und zugewiesen wurden; der Rückgabewert umfasst keine Felder, die gelesen, aber nicht zugewiesen wurden. Ein Rückgabewert von 0 gibt an, dass keine Felder zugewiesen wurden. Der Rückgabewert bei einem Fehler oder beim Erreichen des Endes der Zeichenfolge vor der ersten Konvertierung lautet `EOF`.  
  
 Wenn `buffer` oder `format` ein `NULL`-Zeiger ist, wird der Handler für ungültige Parameter wie in [Parameter Validation (Parameterüberprüfung)](../../c-runtime-library/parameter-validation.md) beschrieben aufgerufen. Wenn die weitere Ausführung zugelassen wird, geben diese Funktionen "– 1" zurück und legen `errno` auf `EINVAL` fest.  
  
 Weitere Informationen über diese und andere Fehlercodes finden Sie unter [errno, _doserrno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Hinweise  
 Die `sscanf_s`-Funktion liest Daten aus `buffer` in den Speicherort, der durch das jeweilige `argument` angegeben wird. Die Argumente nach der Formatzeichenfolge geben Zeiger zu den Variablen an, die einen Typ haben, der einem Typspezifizierer in `format` entspricht. Im Gegensatz zu den weniger sicheren `sscanf`-Versionen ist bei der Verwendung der Typfeldzeichen `c`, `C`, `s`, `S` oder von in `[]` enthaltenen Zeichenfolgensteuerungssätzen ein Puffergrößenparameter erforderlich. Nach jedem Pufferparameter, der dies erfordert, muss die Puffergröße in Zeichen als zusätzlicher Parameter angegeben werden. Beim Einlesen einer Zeichenfolge wird beispielsweise die Puffergröße für diese Zeichenfolge wie folgt übergeben:  
  
 `wchar_t ws[10];`  
  
 `swscanf_s(in_str, L"%9s", ws, (unsigned)_countof(ws)); // buffer size is 10, width specification is 9`  
  
 Die Puffergröße enthält das abschließende NULL-Zeichen. Ein Feld für die Breitenangabe muss verwendet werden, um sicherzustellen, dass das eingelesene Token in den Puffer passt. Wenn kein Feld für die Breiteangabe verwendet wird und das eingelesen Token zu groß für den Puffer ist, wird nichts in diesen Puffer geschrieben.  
  
 Im Fall von Zeichen wird ein einzelnes Zeichen wie folgt gelesen:  
  
 `wchar_t wc;`  
  
 `swscanf_s(in_str, L"%c", &wc, 1);`  
  
 In diesem Beispiel wird ein einzelnes Zeichen aus der Eingabezeichenfolge gelesen und dann in einem Breitzeichenpuffer gespeichert. Wenn mehrere Zeichen für Zeichenfolgen gelesen werden, die nicht mit NULL abschließen, werden ganze Zahlen ohne Vorzeichen für die Breitenangabe und die Puffergröße verwendet.  
  
 `char c[4];`  
  
 `sscanf_s(input, "%4c", &c, (unsigned)_countof(c)); // not null terminated`  
  
 Weitere Informationen finden Sie unter [scanf_s, _scanf_s_l, wscanf_s, _wscanf_s_l](../../c-runtime-library/reference/scanf-s-scanf-s-l-wscanf-s-wscanf-s-l.md) und [scanf-Typenfeldzeichen](../../c-runtime-library/scanf-type-field-characters.md).  
  
> [!NOTE]
>  Der Größenparameter ist vom Typ `unsigned` und nicht vom Typ `size_t`. Wenn Sie für 64-Bit-Ziele kompilieren, verwenden Sie eine statische Umwandlung, um `_countof`- oder `sizeof`-Ergebnisse in die korrekte Größe zu konvertieren.  
  
 Das `format`-Argument steuert die Interpretation der Eingabefelder und hat die gleiche Form und Funktion wie das `format`-Argument für die `scanf_s`-Funktion. Wenn der Kopiervorgang zwischen Zeichenfolgen ausgeführt wird, die sich überschneiden, ist das Verhalten nicht definiert.  
  
 `swscanf_s` ist eine Breitzeichenversion von `sscanf_s;`. Die Argumente für `swscanf_s` sind Zeichenfolgen mit Breitzeichen. `sscanf_s` verarbeitet keine Multibyte-Hexadezimalzeichen. `swscanf_s` verarbeitet keine Unicode-Hexadezimalzeichen in voller Breite (Kompatibilitätszonenzeichen). Andernfalls verhalten sich `swscanf_s` und `sscanf_s` identisch.  
  
 Die Versionen dieser Funktionen mit dem `_l`-Suffix sind beinahe identisch, verwenden jedoch den Gebietsschemaparameter, der anstelle des aktuellen Threadgebietsschemas übergeben wurde.  
  
### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen  
  
|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_stscanf_s`|`sscanf_s`|`sscanf_s`|`swscanf_s`|  
|`_stscanf_s_l`|`_sscanf_s_l`|`_sscanf_s_l`|`_swscanf_s_l`|  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------|  
|`sscanf_s`, `_sscanf_s_l`|\<stdio.h>|  
|`swscanf_s`, `_swscanf_s_l`|\<stdio.h> oder \<wchar.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Beispiel  
  
```  
// crt_sscanf_s.c  
// This program uses sscanf_s to read data items  
// from a string named tokenstring, then displays them.  
  
#include <stdio.h>  
#include <stdlib.h>  
  
int main( void )  
{  
   char  tokenstring[] = "15 12 14...";  
   char  s[81];  
   char  c;  
   int   i;  
   float fp;  
  
   // Input various data from tokenstring:  
   // max 80 character string plus NULL terminator  
   sscanf_s( tokenstring, "%s", s, (unsigned)_countof(s) );  
   sscanf_s( tokenstring, "%c", &c, (unsigned)sizeof(char) );  
   sscanf_s( tokenstring, "%d", &i );  
   sscanf_s( tokenstring, "%f", &fp );  
  
   // Output the data read  
   printf_s( "String    = %s\n", s );  
   printf_s( "Character = %c\n", c );  
   printf_s( "Integer:  = %d\n", i );  
   printf_s( "Real:     = %f\n", fp );  
}  
```  
  
```Output  
String    = 15  
Character = 1  
Integer:  = 15  
Real:     = 15.000000  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Stream-E/A](../../c-runtime-library/stream-i-o.md)   
 [fscanf, _fscanf_l, fwscanf, _fwscanf_l](../../c-runtime-library/reference/fscanf-fscanf-l-fwscanf-fwscanf-l.md)   
 [scanf, _scanf_l, wscanf, _wscanf_l](../../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md)   
 [sprintf, _sprintf_l, swprintf, _swprintf_l, \__swprintf_l](../../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)   
 [snprintf, _snprintf, _snprintf_l, _snwprintf, _snwprintf_l](../../c-runtime-library/reference/snprintf-snprintf-snprintf-l-snwprintf-snwprintf-l.md)
