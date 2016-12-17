---
title: "atoi, _atoi_l, _wtoi, _wtoi_l"
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
  - "_wtoi"
  - "_wtoi_l"
  - "atoi"
  - "_atoi_l"
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
  - "_tstoi"
  - "_wtoi"
  - "_ttoi"
  - "atoi"
  - "_atoi_l"
  - "_wtoi_l"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_atoi_l-Funktion"
  - "ttoi-Funktion"
  - "atoi_l-Funktion"
  - "Zeichenfolgenkonvertierung, in ganze Zahlen"
  - "_wtoi-Funktion"
  - "wtoi_l-Funktion"
  - "tstoi-Funktion"
  - "_ttoi-Funktion"
  - "_tstoi-Funktion"
  - "_wtoi_l-Funktion"
  - "atoi-Funktion"
  - "wtoi-Funktion"
ms.assetid: ad7fda30-28ab-421f-aaad-ef0b8868663a
caps.latest.revision: 22
caps.handback.revision: "20"
ms.author: "corob"
manager: "ghogen"
---
# atoi, _atoi_l, _wtoi, _wtoi_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Konvertiert eine Zeichenfolge die ganze Zahl.  
  
## Syntax  
  
```  
int atoi(  
   const char *str   
);  
int _wtoi(  
   const wchar_t *str   
);  
int _atoi_l(  
   const char *str,  
   _locale_t locale  
);  
int _wtoi_l(  
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
 Jede Funktion gibt den `int`\-Wert zurück, der mit die Eingabezeichen als Zahl erzeugt, interpretiert.  Der Rückgabewert ist 0 für `atoi`  und `_wtoi`, wenn die Eingabe nicht in einen Wert dieses Typs umgewandelt werden kann.  
  
 Im Fall des Überlaufs mit großen negative ganzzahlige Werte, wird `LONG_MIN` zurückgegeben.  `atoi` und `_wtoi` geben `INT_MAX` und `INT_MIN` auf diesen Bedingungen zurück.  In Fällen, in denen alle Werte außerhalb des Gültigkeitsbereichs liegen, wird `errno` auf `ERANGE` festgelegt.  Wenn der Parameter, der übergeben ist, `NULL` ist, wird der ungültige Parameterhandler aufgerufen, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben.  Wenn die weitere Ausführung zugelassen wird, stellen diese Funktionen `errno` auf `EINVAL` ein und geben 0 zurück.  
  
## Hinweise  
 Diese Funktionen konvertieren eine Zeichenfolge in einen ganzzahligen Wert \(`atoi` und `_wtoi`\).  Die Eingabezeichenfolge ist eine Sequenz von Zeichen, die als numerischer Wert des angegebenen Typs interpretiert werden.  Die Funktion beendet das Lesen der Eingabezeichenfolge am ersten Zeichen, das nicht als Teil einer Zahl erkannt wird.  Dieses Zeichen ist möglicherweise darauf NULL\-Zeichen \("\\0" oder L"\\0"\) die Zeichenfolge Beenden.  
  
 Das `str`\-Argument `atoi` und `_wtoi` weist die folgende Form:  
  
 \[`whitespace`\] \[`sign`\] \[`digits`\]\]  
  
 `whitespace` besteht aus Leerzeichen oder Tabulatorzeichen, die ignoriert werden, `sign` ist entweder Pluszeichen \(\+\) oder Minuszeichen \(\-\) und `digits` ist mindestens eine Ziffer.  
  
 Die Versionen dieser Funktionen mit dem `_l`\-Suffix sind beinahe identisch, verwenden jedoch den ihnen übergebenen Gebietsschemaparameter anstelle des aktuellen Gebietsschemas.  Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).  
  
### Zuordnung generischer Textroutinen  
  
|TCHAR.H\-Routine|\_UNICODE & \_MBCS nicht definiert|\_MBCS definiert|\_UNICODE definiert|  
|----------------------|----------------------------------------|----------------------|-------------------------|  
|`_tstoi`|`atoi`|`atoi`|`_wtoi`|  
|`_ttoi`|`atoi`|`atoi`|`_wtoi`|  
  
## Anforderungen  
  
|Routinen|Erforderlicher Header|  
|--------------|---------------------------|  
|`atoi`|\<stdlib.h\>|  
|`_atoi_l`, `_wtoi`, `_wtoi_l`|\<stdlib.h\> oder \<wchar.h\>|  
  
## Beispiel  
 Das Programm zeigt an, wie Zahlen, die als Zeichenfolgen gespeichert werden, auf den numerischen Werten mithilfe der Funktionen `atoi` konvertiert werden können.  
  
```  
// crt_atoi.c  
// This program shows how numbers   
// stored as strings can be converted to  
// numeric values using the atoi functions.  
  
#include <stdlib.h>  
#include <stdio.h>  
#include <errno.h>  
  
int main( void )  
{  
    char    *str = NULL;  
    int     value = 0;  
  
    // An example of the atoi function.  
    str = "  -2309 ";  
    value = atoi( str );  
    printf( "Function: atoi( \"%s\" ) = %d\n", str, value );  
  
    // Another example of the atoi function.  
    str = "31412764";  
    value = atoi( str );  
    printf( "Function: atoi( \"%s\" ) = %d\n", str, value );  
  
    // Another example of the atoi function   
    // with an overflow condition occuring.  
    str = "3336402735171707160320";  
    value = atoi( str );  
    printf( "Function: atoi( \"%s\" ) = %d\n", str, value );  
    if (errno == ERANGE)  
    {  
       printf("Overflow condition occurred.\n");  
    }  
}  
```  
  
  **Funktion: atoi \("\-2309 "\) \= \-2309**  
**Funktion: atoi \("31412764 "\) \= 31412764**  
**Funktion: atoi \("3336402735171707160320 "\) \= 2147483647**  
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