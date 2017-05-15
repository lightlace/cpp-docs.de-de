---
title: _set_printf_count_output | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _set_printf_count_output
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
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- set_printf_count_output
- _set_printf_count_output
dev_langs:
- C++
helpviewer_keywords:
- '%n format'
- set_printf_count_output function
- _set_printf_count_output function
ms.assetid: d8259ec5-764e-42d0-9169-72172e95163b
caps.latest.revision: 8
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
ms.sourcegitcommit: aadbf7d2c6fece48ab29c1b818995464a790c38b
ms.openlocfilehash: 11f0dbe2a4bb67992dd307aea62f79ca8f6b5f73
ms.contentlocale: de-de
ms.lasthandoff: 03/07/2017

---
# <a name="setprintfcountoutput"></a>_set_printf_count_output
Aktivieren oder Deaktivieren der Unterstützung des `%n`-Formats in den Funktionen der [printf, _printf_l, wprintf, _wprintf_l](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)-Familie.  
  
## <a name="syntax"></a>Syntax  
  
```  
int _set_printf_count_output(  
   int enable  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `enable`  
 Ein Wert ungleich null zum Aktivieren der `%n`-Unterstützung, 0 zum Deaktivieren der `%n`-Unterstützung.  
  
## <a name="property-valuereturn-value"></a>Eigenschaftswert/Rückgabewert  
 Der Status der `%n`-Unterstützung vor dem Aufrufen dieser Funktion: ungleich null, wenn die `%n`-Unterstützung aktiviert wurde, 0, wenn sie deaktiviert wurde.  
  
## <a name="remarks"></a>Hinweise  
 Aus Sicherheitsgründen ist die Unterstützung für den `%n`-Formatbezeichner standardmäßig in `printf` und dessen Varianten deaktiviert. Wenn `%n` in einer `printf`-Formatzeichenfolge festgestellt wird, wird gemäß Standardverhalten der Handler für ungültige Parameter wie in [Parameter Validation (Parameterüberprüfung)](../../c-runtime-library/parameter-validation.md) beschrieben aufgerufen. Aufrufen `_set_printf_count_output` mit einem Argument ungleich 0 führt dazu, dass `printf`-Produktfamilie Funktionen zum Interpretieren `%n` wie beschrieben in [Syntax der Formatangabe: printf- und Wprintf-Funktionen](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md).  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------|  
|`_set_printf_count_output`|\<stdio.h>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="example"></a>Beispiel  
  
```C  
// crt_set_printf_count_output.c  
#include <stdio.h>  
  
int main()  
{  
   int e;  
   int i;  
   e = _set_printf_count_output( 1 );  
   printf( "%%n support was %sabled.\n",  
        e ? "en" : "dis" );  
   printf( "%%n support is now %sabled.\n",  
        _get_printf_count_output() ? "en" : "dis" );  
   printf( "12345%n6789\n", &i ); // %n format should set i to 5  
   printf( "i = %d\n", i );  
}  
```  
  
```Output  
%n support was disabled.  
%n support is now enabled.  
123456789  
i = 5  
```  
  
## <a name="see-also"></a>Siehe auch  
 [_get_printf_count_output](../../c-runtime-library/reference/get-printf-count-output.md)
