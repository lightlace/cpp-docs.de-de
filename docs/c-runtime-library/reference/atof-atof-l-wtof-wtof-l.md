---
title: "atof, _atof_l, _wtof, _wtof_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_wtof_l"
  - "atof"
  - "_atof_l"
  - "_wtof"
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
  - "_tstof"
  - "_ttof"
  - "atof"
  - "stdlib/atof"
  - "math/atof"
  - "_atof_l"
  - "stdlib/_atof_l"
  - "math/_atof_l"
  - "_wtof"
  - "corecrt_wstdlib/_wtof"
  - "_wtof_l"
  - "corecrt_wstdlib/_wtof_l"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "tstof-Funktion"
  - "atof_l-Funktion"
  - "_atof_l-Funktion"
  - "atof-Funktion"
  - "_tstof-Funktion"
  - "_ttof-Funktion"
  - "wtof-Funktion"
  - "_wtof_l-Funktion"
  - "ttof-Funktion"
  - "wtof_l-Funktion"
  - "_wtof-Funktion"
  - "Zeichenfolgenkonvertierung, in Gleitkommawerte"
ms.assetid: eb513241-c9a9-4f5c-b7e7-a49b14abfb75
caps.latest.revision: 26
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 26
---
# atof, _atof_l, _wtof, _wtof_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Konvertieren einer Zeichenfolge, um sich zu verdoppeln.  
  
## Syntax  
  
```  
double atof(  
   const char *str   
);  
double _atof_l(  
   const char *str,  
   _locale_t locale  
);  
double _wtof(  
   const wchar_t *str   
);  
double _wtof_l(  
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
 Jede Funktion gibt den `double`\-Wert zurück, der mit die Eingabezeichen als Zahl erzeugt, interpretiert.  Der Rückgabewert ist 0,0, wenn die Eingabe nicht in einen Wert dieses Typs umgewandelt werden kann.  
  
 In allen außerhalb des Gültigkeitsbereichs liegenden Fällen wird errno auf `ERANGE` festgelegt.  Wenn der Parameter, der übergeben ist, `NULL` ist, wird der ungültige Parameterhandler aufgerufen, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben.  Wenn die weitere Ausführung zugelassen wird, stellen diese Funktionen `errno` auf `EINVAL` ein und geben 0 zurück.  
  
## Hinweise  
 Diese Funktionen konvertieren eine Zeichenfolge in einen mit doppelter Genauigkeit, Gleitkommawert.  
  
 Die Eingabezeichenfolge ist eine Sequenz von Zeichen, die als numerischer Wert des angegebenen Typs interpretiert werden.  Die Funktion beendet das Lesen der Eingabezeichenfolge am ersten Zeichen, das nicht als Teil einer Zahl erkannt wird.  Dieses Zeichen ist möglicherweise darauf NULL\-Zeichen \("\\0" oder L"\\0"\) die Zeichenfolge Beenden.  
  
 Das Argument `str` von `atof` und `_wtof` weist die folgende Form:  
  
 \[`whitespace`\] \[`sign`\] \[`digits`\] \[`.digits`\] \[ {`d` &#124; `D` &#124; `e` &#124; `E` }\[`sign`\]`digits`\]  
  
 `whitespace` besteht aus Leerzeichen oder Tabstoppzeichen, die ignoriert; `sign` ist entweder Pluszeichen \(\+\) oder Minuszeichen \(\-\); und `digits` sind eine oder mehrere Dezimalstellen.  Wenn keine Ziffern vor dem Dezimaltrennzeichen werden, muss mindestens von nach dem Dezimaltrennzeichen werden.  Die Dezimalstellen werden von einem Exponenten folgen, der einführenden einem Buchstaben \(`d`, `D`, `e` oder `E`\) und einer optional dezimalen ganze Zahl mit Vorzeichen besteht.  
  
 Die Versionen dieser Funktionen mit dem `_l`\-Suffix sind beinahe identisch, verwenden jedoch den ihnen übergebenen Gebietsschemaparameter anstelle des aktuellen Gebietsschemas.  
  
### Zuordnung generischer Textroutinen  
  
|TCHAR.H\-Routine|\_UNICODE & \_MBCS nicht definiert|\_MBCS definiert|\_UNICODE definiert|  
|----------------------|----------------------------------------|----------------------|-------------------------|  
|`_tstof`|`atof`|`atof`|`_wtof`|  
|`_ttof`|`atof`|`atof`|`_wtof`|  
  
## Anforderungen  
  
|Routinen|Erforderlicher Header|  
|--------------|---------------------------|  
|`atof`|\<math.h und\> stdlib.h \<\>|  
|`_atof_l`|\<math.h und\> stdlib.h \<\>|  
|`_wtof`, `_wtof_l`|\<stdlib.h\> oder \<wchar.h\>|  
  
## Beispiel  
 Das Programm zeigt an, wie Zahlen, die als Zeichenfolgen gespeichert werden, auf den numerischen Werten mit der `atof`\-Funktion konvertiert werden können.  
  
```  
// crt_atof.c  
//  
// This program shows how numbers stored as   
// strings can be converted to numeric  
// values using the atof function.  
  
#include <stdlib.h>  
#include <stdio.h>  
  
int main( void )  
{  
    char    *str = NULL;  
    double  value = 0;  
  
    // An example of the atof function  
    // using leading and training spaces.  
    str = "  3336402735171707160320 ";  
    value = atof( str );  
    printf( "Function: atof( \"%s\" ) = %e\n", str, value );  
  
    // Another example of the atof function  
    // using the 'd' exponential formatting keyword.  
    str = "3.1412764583d210";  
    value = atof( str );  
    printf( "Function: atof( \"%s\" ) = %e\n", str, value );  
  
    // An example of the atof function  
    // using the 'e' exponential formatting keyword.  
    str = "  -2309.12E-15";  
    value = atof( str );  
    printf( "Function: atof( \"%s\" ) = %e\n", str, value );  
  
}  
```  
  
  **Funktion: atof \("3336402735171707160320 "\) \= 3.336403e\+021**  
**Funktion: atof \("3.1412764583d210"\) \= 3.141276e\+210**  
**Funktion: atof \("\-2309.12E\-15"\) \= \-2.309120e\-012**   
## .NET Framework-Entsprechung  
  
-   [System::Convert::ToSingle](https://msdn.microsoft.com/en-us/library/system.convert.tosingle.aspx)  
  
-   [System::Convert::ToDouble](https://msdn.microsoft.com/en-us/library/system.convert.todouble.aspx)  
  
## Siehe auch  
 [Datenkonvertierung](../../c-runtime-library/data-conversion.md)   
 [Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)   
 [Locale](../../c-runtime-library/locale.md)   
 [\_ecvt](../../c-runtime-library/reference/ecvt.md)   
 [\_fcvt](../../c-runtime-library/reference/fcvt.md)   
 [\_gcvt](../../c-runtime-library/reference/gcvt.md)   
 [setlocale, \_wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)   
 [\_atodbl, \_atodbl\_l, \_atoldbl, \_atoldbl\_l, \_atoflt, \_atoflt\_l](../../c-runtime-library/reference/atodbl-atodbl-l-atoldbl-atoldbl-l-atoflt-atoflt-l.md)