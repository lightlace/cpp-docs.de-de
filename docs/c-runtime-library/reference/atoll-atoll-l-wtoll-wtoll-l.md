---
title: atoll, _atoll_l, _wtoll, _wtoll_l | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _wtoll
- _atoll_l
- _wtoll_l
- atoll
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
- _tstoll_l
- _wtoll
- _atoll_l
- _ttoll
- _tstoll
- _wtoll_l
- atoll
dev_langs:
- C++
helpviewer_keywords:
- atoll function
- _wtoll_l function
- _wtoll function
- _atoll_l function
ms.assetid: 5e85fcac-b351-4882-bff2-6e7c469b7fa8
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
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
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: e707c06f06015a684e968367f61e7e763ff87a6d
ms.contentlocale: de-de
ms.lasthandoff: 04/01/2017

---
# <a name="atoll-atolll-wtoll-wtolll"></a>atoll, _atoll_l, _wtoll, _wtoll_l
Konvertiert eine Zeichenfolge in eine `long long`-Ganzzahl.  
  
## <a name="syntax"></a>Syntax  
  
```  
long long atoll(  
   const char *str   
);  
long long _wtoll(  
   const wchar_t *str   
);  
long long _atoll_l(  
   const char *str,  
   _locale_t locale  
);  
long long _wtoll_l(  
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
 Jede Funktion gibt den `long long`-Wert zurück, der erstellt wird, indem die Eingabezeichen als Zahl interpretiert werden. Der Rückgabewert für `atoll` ist 0, wenn die Eingabe nicht in einen Wert dieses Typs umgewandelt werden kann.  
  
 Bei einem Überlauf mit großen positiven ganzzahligen Werten gibt `atoll``LLONG_MAX` zurück, und bei einem Überlauf mit großen negativen ganzzahligen Werten gibt `LLONG_MIN` zurück.  
  
 In Fällen, in denen alle Werte außerhalb des Gültigkeitsbereichs liegen, wird `errno` auf `ERANGE` festgelegt. Wenn der übergebene Parameter `NULL` ist, wird der Handler für ungültige Parameter aufgerufen, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben. Wenn die weitere Ausführung zugelassen wird, stellen diese Funktionen `errno` auf `EINVAL` ein und geben 0 zurück.  
  
## <a name="remarks"></a>Hinweise  
 Diese Funktionen konvertieren eine Zeichenfolge in eine `long long`-Ganzzahl.  
  
 Die Eingabezeichenfolge ist eine Sequenz von Zeichen, die als numerischer Wert des angegebenen Typs interpretiert werden. Die Funktion beendet das Lesen der Eingabezeichenfolge am ersten Zeichen, das nicht als Teil einer Zahl erkannt wird. Dieses Zeichen kann das NULL-Zeichen ('\0' or L'\0') sein, das die Zeichenfolge beendet.  
  
 Das `str`-Argument für `atoll` weist folgende Form auf:  
  
```  
[whitespace] [sign] [digits]  
```  
  
 Ein `whitespace` besteht aus Leerzeichen oder Tabulatorzeichen, die ignoriert werden. `sign` ist entweder Pluszeichen (+) oder Minuszeichen (-) und `digits` sind eine oder mehrere Ziffern.  
  
 `_wtoll` ist mit `atoll` identisch, außer dass es eine Zeichenfolge mit Breitzeichen als Parameter verwendet.  
  
 Die Versionen dieser Funktionen mit dem `_l`-Suffix sind identisch mit den Versionen, die keinen Suffix haben, verwenden jedoch den Gebietsschemaparameter, der anstelle des aktuellen Gebietsschemas übergeben wurde. Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).  
  
### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen  
  
|Tchar.h-Routine|_UNICODE und _MBCS nicht definiert|_MBCS definiert|_UNICODE definiert|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_tstoll`|`atoll`|`atoll`|`_wtoll`|  
|`_tstoll_l`|`_atoll_l`|`_atoll_l`|`_wtoll_l`|  
|`_ttoll`|`_atoll`|`_atoll`|`_wtoll`|  
  
## <a name="requirements"></a>Anforderungen  
  
|Routinen|Erforderlicher Header|  
|--------------|---------------------|  
|`atoll`, `_atoll_l`|\<stdlib.h>|  
|`_wtoll`, `_wtoll_l`|\<stdlib.h> oder \<wchar.h>|  
  
## <a name="example"></a>Beispiel  
 Dieses Programm zeigt, wie die `atoll`-Funktionen verwendet werden, um als Zeichenfolgen gespeicherte Zahlen in numerische Werte zu konvertieren.  
  
```  
// crt_atoll.c  
// Build with: cl /W4 /Tc crt_atoll.c  
// This program shows how to use the atoll   
// functions to convert numbers stored as   
// strings to numeric values.  
#include <stdlib.h>  
#include <stdio.h>  
#include <errno.h>  
  
int main(void)  
{  
    char *str = NULL;  
    long long value = 0;  
  
    // An example of the atoll function  
    // with leading and trailing white spaces.  
    str = "  -27182818284 ";  
    value = atoll(str);  
    printf("Function: atoll(\"%s\") = %lld\n", str, value);  
  
    // Another example of the atoll function   
    // with an arbitrary decimal point.  
    str = "314127.64";  
    value = atoll(str);  
    printf("Function: atoll(\"%s\") = %lld\n", str, value);  
  
    // Another example of the atoll function  
    // with an overflow condition occurring.  
    str = "3336402735171707160320";  
    value = atoll(str);  
    printf("Function: atoll(\"%s\") = %lld\n", str, value);  
    if (errno == ERANGE)  
    {  
       printf("Overflow condition occurred.\n");  
    }  
}  
```  
  
```Output  
Function: atoll("  -27182818284 ") = -27182818284  
Function: atoll("314127.64") = 314127  
Function: atoll("3336402735171707160320") = 9223372036854775807  
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
