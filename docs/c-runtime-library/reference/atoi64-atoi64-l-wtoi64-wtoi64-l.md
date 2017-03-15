---
title: "_atoi64, _atoi64_l, _wtoi64, _wtoi64_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_atoi64_l"
  - "_wtoi64"
  - "_atoi64"
  - "_wtoi64_l"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
  - "api-ms-win-crt-convert-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_atoi64"
  - "_tstoi64"
  - "_ttoi64"
  - "wtoi64"
  - "_tstoi64_l"
  - "atoi64"
  - "_wtoi64_l"
  - "_wtoi64"
  - "wtoi64_l"
  - "_atoi64_l"
  - "atoi64_l"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "tstoi64-Funktion"
  - "wtoi64-Funktion"
  - "atoi64_l-Funktion"
  - "_ttoi64-Funktion"
  - "Zeichenfolgenkonvertierung, in ganze Zahlen"
  - "wtoi64_l-Funktion"
  - "atoi64-Funktion"
  - "_tstoi64-Funktion"
  - "_atoi64_l-Funktion"
  - "_wtoi64_l-Funktion"
  - "ttoi64-Funktion"
  - "_wtoi64-Funktion"
  - "_atoi64-Funktion"
ms.assetid: 2c3e30fd-545d-4222-8364-0c5905df9526
caps.latest.revision: 24
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 24
---
# _atoi64, _atoi64_l, _wtoi64, _wtoi64_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Konvertiert eine Zeichenfolge in eine 64\-Bit\-Ganzzahl.  
  
## Syntax  
  
```  
__int64 _atoi64(  
   const char *str   
);  
__int64 _wtoi64(  
   const wchar_t *str   
);  
__int64 _atoi64_l(  
   const char *str,  
   _locale_t locale  
);  
__int64 _wtoi64_l(  
   const wchar_t *str,  
   _locale_t locale  
);  
```  
  
#### Parameter  
 `str`  
 Zu konvertierende Zeichenfolge.  
  
 `locale`  
 Zu verwendendes Gebietsschema.  
  
## Rückgabewert  
 Jede Funktion gibt den `__int64`\-Wert zurück, der mit die Eingabezeichen als Zahl erzeugt, interpretiert.  Der Rückgabewert ist 0 für `_atoi64`, wenn die Eingabe nicht in einen Wert dieses Typs umgewandelt werden kann.  
  
 Im Fall des Überlaufs mit großen positiven Ganzzahlwerte, gibt `_atoi64``I64_MAX` und `I64_MIN` in den Ereignisdaten des Überlaufs mit großen negative ganzzahlige Werte zurück.  
  
 In Fällen, in denen alle Werte außerhalb des Gültigkeitsbereichs liegen, wird `errno` auf `ERANGE` festgelegt.  Wenn der Parameter, der übergeben ist, `NULL` ist, wird der ungültige Parameterhandler aufgerufen, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben.  Wenn die weitere Ausführung zugelassen wird, stellen diese Funktionen `errno` auf `EINVAL` ein und geben 0 zurück.  
  
## Hinweise  
 Diese Funktionen konvertieren eine Zeichenfolge in einen 64\-Bit\-Ganzzahlwert.  
  
 Die Eingabezeichenfolge ist eine Sequenz von Zeichen, die als numerischer Wert des angegebenen Typs interpretiert werden.  Die Funktion beendet das Lesen der Eingabezeichenfolge am ersten Zeichen, das nicht als Teil einer Zahl erkannt wird.  Dieses Zeichen ist das NULL\-Zeichen \("\\0" oder L"\\0"\) die Zeichenfolge Beenden.  
  
 Das `str`\-Argument für `_atoi64` weist folgende Form auf:  
  
```  
[whitespace] [sign] [digits]]  
```  
  
 `whitespace` besteht aus Leerzeichen oder Tabulatorzeichen, die ignoriert werden, `sign` ist entweder Pluszeichen \(\+\) oder Minuszeichen \(\-\) und `digits` ist mindestens eine Ziffer.  
  
 `_wtoi64` ist mit `_atoi64` identisch, außer dass es eine Zeichenfolge mit Breitzeichen als Parameter verwendet.  
  
 Die Versionen dieser Funktionen mit dem `_l`\-Suffix sind beinahe identisch, verwenden jedoch den ihnen übergebenen Gebietsschemaparameter anstelle des aktuellen Gebietsschemas.  Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).  
  
### Zuordnung generischer Textroutinen  
  
|Tchar.h\-Routine|\_UNICODE und \_MBCS nicht definiert|\_MBCS definiert|\_UNICODE definiert|  
|----------------------|------------------------------------------|----------------------|-------------------------|  
|`_tstoi64`|`_atoi64`|`_atoi64`|`_wtoi64`|  
|`_ttoi64`|`_atoi64`|`_atoi64`|`_wtoi64`|  
  
## Anforderungen  
  
|Routinen|Erforderlicher Header|  
|--------------|---------------------------|  
|`_atoi64`, `_atoi64_l`|\<stdlib.h\>|  
|`_wtoi64`, `_wtoi64_l`|\<stdlib.h\> oder \<wchar.h\>|  
  
## Beispiel  
 Das Programm zeigt an, wie Zahlen, die als Zeichenfolgen gespeichert werden, auf den numerischen Werten mithilfe der Funktionen `_atoi64` konvertiert werden können.  
  
```  
// crt_atoi64.c  
// This program shows how numbers stored as  
// strings can be converted to numeric values  
// using the _atoi64 functions.  
#include <stdlib.h>  
#include <stdio.h>  
#include <errno.h>  
  
int main( void )  
{  
    char    *str = NULL;  
    __int64 value = 0;  
  
    // An example of the _atoi64 function  
    // with leading and trailing white spaces.  
    str = "  -2309 ";  
    value = _atoi64( str );  
    printf( "Function: _atoi64( \"%s\" ) = %d\n", str, value );  
  
    // Another example of the _atoi64 function   
    // with an arbitrary decimal point.  
    str = "314127.64";  
    value = _atoi64( str );  
    printf( "Function: _atoi64( \"%s\" ) = %d\n", str, value );  
  
    // Another example of the _atoi64 function  
    // with an overflow condition occurring.  
    str = "3336402735171707160320";  
    value = _atoi64( str );  
    printf( "Function: _atoi64( \"%s\" ) = %d\n", str, value );  
    if (errno == ERANGE)  
    {  
       printf("Overflow condition occurred.\n");  
    }  
}  
```  
  
  **Funktion: \_atoi64 \("\-2309 "\) \= \-2309**  
**Funktion: \_atoi64 \("314127,64 "\) \= 314127**  
**Funktion: \_atoi64 \("3336402735171707160320 "\) \= \-1**  
**Overflow condition occurred.**   
## .NET Framework-Entsprechung  
  
-   [System::Convert::ToInt64](https://msdn.microsoft.com/en-us/library/system.convert.toint64.aspx)  
  
-   [System::Convert::ToUInt64](https://msdn.microsoft.com/en-us/library/system.convert.touint64.aspx)  
  
## Siehe auch  
 [Datenkonvertierung](../../c-runtime-library/data-conversion.md)   
 [Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)   
 [Locale](../../c-runtime-library/locale.md)   
 [\_ecvt](../../c-runtime-library/reference/ecvt.md)   
 [\_fcvt](../../c-runtime-library/reference/fcvt.md)   
 [\_gcvt](../../c-runtime-library/reference/gcvt.md)   
 [setlocale, \_wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)   
 [\_atodbl, \_atodbl\_l, \_atoldbl, \_atoldbl\_l, \_atoflt, \_atoflt\_l](../../c-runtime-library/reference/atodbl-atodbl-l-atoldbl-atoldbl-l-atoflt-atoflt-l.md)