---
title: "atol, _atol_l, _wtol, _wtol_l"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
apiname: 
  - "atol"
  - "_wtol_l"
  - "_wtol"
  - "_atol_l"
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
  - "_atol_l"
  - "_ttol_l"
  - "_tstol_l"
  - "_tstol"
  - "_wtol"
  - "_ttol"
  - "_wtol_l"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "tstol-Funktion"
  - "atol-Funktion"
  - "ttol-Funktion"
  - "_atol_l-Funktion"
  - "_tstol_l-Funktion"
  - "Zeichenfolgenkonvertierung, in ganze Zahlen"
  - "_tstol-Funktion"
  - "_ttol-Funktion"
  - "_ttol_l-Funktion"
  - "atol_l-Funktion"
  - "wtol_l-Funktion"
  - "_wtol_l-Funktion"
  - "wtol-Funktion"
  - "_wtol-Funktion"
ms.assetid: cedfc21c-2d64-4e9c-bd04-bdf60b12db46
caps.latest.revision: 22
caps.handback.revision: "20"
ms.author: "corob"
manager: "ghogen"
---
# atol, _atol_l, _wtol, _wtol_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Konvertiert eine Zeichenfolge in eine lange ganze Zahl.  
  
## Syntax  
  
```  
long atol(  
   const char *str   
);  
long _atol_l(  
   const char *str,  
   _locale_t locale  
);  
long _wtol(  
   const wchar_t *str   
);  
long _wtol_l(  
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
 Jede Funktion gibt den `long`\-Wert zurück, der mit die Eingabezeichen als Zahl erzeugt, interpretiert.  Der Rückgabewert ist 0L für `atol`, wenn die Eingabe nicht in einen Wert dieses Typs umgewandelt werden kann.  
  
 Im Fall des Überlaufs mit großen positiven Ganzzahlwerte, gibt `atol``LONG_MAX` zurück; im Falle des Überlaufs mit großen negative ganzzahlige Werte, wird `LONG_MIN` zurückgegeben.  In Fällen, in denen alle Werte außerhalb des Gültigkeitsbereichs liegen, wird `errno` auf `ERANGE` festgelegt.  Wenn der Parameter, der übergeben ist, `NULL` ist, wird der ungültige Parameterhandler aufgerufen, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben.  Wenn die weitere Ausführung zugelassen wird, stellen diese Funktionen `errno` auf `EINVAL` ein und geben 0 zurück.  
  
## Hinweise  
 Diese Funktionen konvertieren eine Zeichenfolge in einem long ganzzahligen Wert \(`atol`\).  
  
 Die Eingabezeichenfolge ist eine Sequenz von Zeichen, die als numerischer Wert des angegebenen Typs interpretiert werden.  Die Funktion beendet das Lesen der Eingabezeichenfolge am ersten Zeichen, das nicht als Teil einer Zahl erkannt wird.  Dieses Zeichen ist möglicherweise das `NULL` Zeichen \("\\0" oder L"\\0"\) die Zeichenfolge beenden.  
  
 Das `str`\-Argument für `atol` weist folgende Form auf:  
  
 \[`whitespace`\] \[`sign`\] \[`digits`\]\]  
  
 `whitespace` besteht aus Leerzeichen oder Tabulatorzeichen, die ignoriert werden, `sign` ist entweder Pluszeichen \(\+\) oder Minuszeichen \(\-\) und `digits` ist mindestens eine Ziffer.  
  
 `_wtol` ist mit `atol` identisch, es lässt eine Zeichenfolge mit Breitzeichen.  
  
 Die Versionen dieser Funktionen mit dem `_l`\-Suffix sind beinahe identisch, verwenden jedoch den ihnen übergebenen Gebietsschemaparameter anstelle des aktuellen Gebietsschemas.  Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).  
  
### Zuordnung generischer Textroutinen  
  
|TCHAR.H\-Routine|\_UNICODE & \_MBCS nicht definiert|\_MBCS definiert|\_UNICODE definiert|  
|----------------------|----------------------------------------|----------------------|-------------------------|  
|`_tstol`|`atol`|`atol`|`_wtol`|  
|`_ttol`|`atol`|`atol`|`_wtol`|  
  
## Anforderungen  
  
|Routinen|Erforderlicher Header|  
|--------------|---------------------------|  
|`atol`|\<stdlib.h\>|  
|`_atol_l`, `_wtol`, `_wtol_l`|\<stdlib.h und\> wchar.h \<\>|  
  
## Beispiel  
 Das Programm zeigt an, wie Zahlen, die als Zeichenfolgen gespeichert werden, auf den numerischen Werten mit der `atol`\-Funktion konvertiert werden können.  
  
```  
// crt_atol.c  
// This program shows how numbers stored as  
// strings can be converted to numeric values  
// using the atol functions.  
#include <stdlib.h>  
#include <stdio.h>  
#include <errno.h>  
  
int main( void )  
{  
    char    *str = NULL;  
    long    value = 0;  
  
    // An example of the atol function  
    // with leading and trailing white spaces.  
    str = "  -2309 ";  
    value = atol( str );  
    printf( "Function: atol( \"%s\" ) = %d\n", str, value );  
  
    // Another example of the atol function   
    // with an arbitrary decimal point.  
    str = "314127.64";  
    value = atol( str );  
    printf( "Function: atol( \"%s\" ) = %d\n", str, value );  
  
    // Another example of the atol function  
    // with an overflow condition occurring.  
    str = "3336402735171707160320";  
    value = atol( str );  
    printf( "Function: atol( \"%s\" ) = %d\n", str, value );  
    if (errno == ERANGE)  
    {  
       printf("Overflow condition occurred.\n");  
    }  
}  
```  
  
  **Funktion: atol \("\-2309 "\) \= \-2309**  
**Funktion: atol \("314127,64 "\) \= 314127**  
**Funktion: atol \("3336402735171707160320 "\) \= 2147483647**  
**Overflow condition occurred.**   
## .NET Framework-Entsprechung  
  
-   [System::Convert::ToInt32](https://msdn.microsoft.com/en-us/library/system.convert.toint32.aspx)  
  
-   [System::Convert::ToUInt32](https://msdn.microsoft.com/en-us/library/system.convert.touint32.aspx)  
  
## Siehe auch  
 [Datenkonvertierung](../../c-runtime-library/data-conversion.md)   
 [Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)   
 [Locale](../../c-runtime-library/locale.md)   
 [\_ecvt](../../c-runtime-library/reference/ecvt.md)   
 [\_fcvt](../../c-runtime-library/reference/fcvt.md)   
 [\_gcvt](../../c-runtime-library/reference/gcvt.md)   
 [setlocale, \_wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)   
 [\_atodbl, \_atodbl\_l, \_atoldbl, \_atoldbl\_l, \_atoflt, \_atoflt\_l](../../c-runtime-library/reference/atodbl-atodbl-l-atoldbl-atoldbl-l-atoflt-atoflt-l.md)