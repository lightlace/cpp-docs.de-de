---
title: _atoi64, _atoi64_l, _wtoi64, _wtoi64_l | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _atoi64_l
- _wtoi64
- _atoi64
- _wtoi64_l
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
- _atoi64
- _tstoi64
- _ttoi64
- wtoi64
- _tstoi64_l
- atoi64
- _wtoi64_l
- _wtoi64
- wtoi64_l
- _atoi64_l
- atoi64_l
dev_langs:
- C++
helpviewer_keywords:
- tstoi64 function
- wtoi64 function
- atoi64_l function
- _ttoi64 function
- string conversion, to integers
- wtoi64_l function
- atoi64 function
- _tstoi64 function
- _atoi64_l function
- _wtoi64_l function
- ttoi64 function
- _wtoi64 function
- _atoi64 function
ms.assetid: 2c3e30fd-545d-4222-8364-0c5905df9526
caps.latest.revision: 24
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: 749ce35fdb4ed530bf301539b13ba3cb0471b996
ms.contentlocale: de-de
ms.lasthandoff: 04/01/2017

---
# <a name="atoi64-atoi64l-wtoi64-wtoi64l"></a>_atoi64, _atoi64_l, _wtoi64, _wtoi64_l
Konvertiert eine Zeichenfolge in eine 64-Bit-Ganzzahl.  
  
## <a name="syntax"></a>Syntax  
  
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
  
#### <a name="parameters"></a>Parameter  
 `str`  
 Zu konvertierende Zeichenfolge.  
  
 `locale`  
 Zu verwendendes Gebietsschema.  
  
## <a name="return-value"></a>Rückgabewert  
 Jede Funktion gibt den `__int64`-Wert zurück, der erstellt wird, indem die Eingabezeichen als Zahl interpretiert werden. Der Rückgabewert ist für `_atoi64` 0, wenn die Eingabe nicht in einen Wert dieses Typs umgewandelt werden kann.  
  
 Im Fall eines Überlaufs mit großen positiven ganzzahligen Werten gibt `_atoi64``I64_MAX` zurück, und im Fall eines Überlaufs mit großen negativen ganzzahligen Werten wird `I64_MIN` zurückgegeben.  
  
 In Fällen, in denen alle Werte außerhalb des Gültigkeitsbereichs liegen, wird `errno` auf `ERANGE` festgelegt. Wenn der übergebene Parameter `NULL` ist, wird der Handler für ungültige Parameter aufgerufen, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben. Wenn die weitere Ausführung zugelassen wird, stellen diese Funktionen `errno` auf `EINVAL` ein und geben 0 zurück.  
  
## <a name="remarks"></a>Hinweise  
 Diese Funktionen konvertieren eine Zeichenfolge in eine 64-Bit-Ganzzahl.  
  
 Die Eingabezeichenfolge ist eine Sequenz von Zeichen, die als numerischer Wert des angegebenen Typs interpretiert werden. Die Funktion beendet das Lesen der Eingabezeichenfolge am ersten Zeichen, das nicht als Teil einer Zahl erkannt wird. Möglicherweise ist dies das Zeichen NULL ('\0' oder L'\0'), das am Ende der Zeichenfolge steht.  
  
 Das `str`-Argument für `_atoi64` weist folgende Form auf:  
  
```  
[whitespace] [sign] [digits]]  
```  
  
 Ein `whitespace` besteht aus Leerzeichen oder Tabulatorzeichen, die ignoriert werden. `sign` ist entweder Pluszeichen (+) oder Minuszeichen (-) und `digits` sind eine oder mehrere Ziffern.  
  
 `_wtoi64` ist mit `_atoi64` identisch, außer dass es eine Zeichenfolge mit Breitzeichen als Parameter verwendet.  
  
 Die Versionen dieser Funktionen mit dem `_l`-Suffix sind beinahe identisch, verwenden jedoch den ihnen übergebenen Gebietsschemaparameter anstelle des aktuellen Gebietsschemas. Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).  
  
### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen  
  
|Tchar.h-Routine|_UNICODE und _MBCS nicht definiert|_MBCS definiert|_UNICODE definiert|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_tstoi64`|`_atoi64`|`_atoi64`|`_wtoi64`|  
|`_ttoi64`|`_atoi64`|`_atoi64`|`_wtoi64`|  
  
## <a name="requirements"></a>Anforderungen  
  
|Routinen|Erforderlicher Header|  
|--------------|---------------------|  
|`_atoi64`, `_atoi64_l`|\<stdlib.h>|  
|`_wtoi64`, `_wtoi64_l`|\<stdlib.h> oder \<wchar.h>|  
  
## <a name="example"></a>Beispiel  
 Dieses Programm zeigt, wie die `_atoi64`-Funktion verwendet wird, um als Zeichenfolgen gespeicherte Zahlen in numerische Werte zu konvertieren.  
  
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
  
```Output  
Function: _atoi64( "  -2309 " ) = -2309  
Function: _atoi64( "314127.64" ) = 314127  
Function: _atoi64( "3336402735171707160320" ) = -1  
Overflow condition occurred.  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Datenkonvertierung](../../c-runtime-library/data-conversion.md)   
 [Gleitkomma-Unterstützung](../../c-runtime-library/floating-point-support.md)   
 [Locale](../../c-runtime-library/locale.md)   
 [_ecvt](../../c-runtime-library/reference/ecvt.md)   
 [_fcvt](../../c-runtime-library/reference/fcvt.md)   
 [_gcvt](../../c-runtime-library/reference/gcvt.md)   
 [setlocale, _wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)   
 [_atodbl, _atodbl_l, _atoldbl, _atoldbl_l, _atoflt, _atoflt_l](../../c-runtime-library/reference/atodbl-atodbl-l-atoldbl-atoldbl-l-atoflt-atoflt-l.md)
