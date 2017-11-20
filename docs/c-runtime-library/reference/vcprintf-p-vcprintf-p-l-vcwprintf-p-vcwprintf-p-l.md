---
title: _vcprintf_p, _vcprintf_p_l, _vcwprintf_p, _vcwprintf_p_l | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _vcprintf_p
- _vcwprintf_p_l
- _vcprintf_p_l
- _vcwprintf_p
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
- vcwprintf_p
- vcprintf_p_l
- _vcprintf_p
- _vcprintf_p_l
- vcwprintf_p_l
- vcprintf_p
- _vcwprintf_p
- _vcwprintf_p_l
dev_langs: C++
helpviewer_keywords:
- _vtcprintf_p_l function
- vcprintf_p_l function
- _vcprintf_p_l function
- vtcprintf_p_l function
- vcprintf_p function
- _vcwprintf_p function
- _vcprintf_p function
- vcwprintf_p function
- vcwprintf_p_l function
- vtcprintf_p function
- _vcwprintf_p_l function
- _vtcprintf_p function
ms.assetid: 611024cc-90e7-41db-8e85-145ca95012b1
caps.latest.revision: "20"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: a04c78f70f1d1338e1c5578b4cb9a641aea30c73
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="vcprintfp-vcprintfpl-vcwprintfp-vcwprintfpl"></a>_vcprintf_p, _vcprintf_p_l, _vcwprintf_p, _vcwprintf_p_l
Schreibt formatierte Ausgabe in die Konsole unter Verwendung eines Zeigers auf eine Liste von Argumenten und unterstützt positionelle Parameter in der Formatzeichenfolge.  
  
> [!IMPORTANT]
>  Diese API kann nicht in Anwendungen verwendet werden, die in Windows-Runtime ausgeführt werden. Weitere Informationen finden Sie unter [In /ZW nicht unterstützte CRT-Funktionen](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## <a name="syntax"></a>Syntax  
  
```  
int _vcprintf_p(  
   const char* format,  
   va_list argptr  
);  
int _vcprintf_p_l(  
   const char* format,  
   locale_t locale,  
   va_list argptr  
);  
int _vcwprintf_p(  
   const wchar_t* format,  
   va_list argptr  
);  
int _vcwprintf_p_l(  
   const wchar_t* format,  
   locale_t locale,  
   va_list argptr  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `format`  
 Die Formatangabe.  
  
 `argptr`  
 Ein Zeiger auf eine Liste der Argumente.  
  
 `locale`  
 Das zu verwendende Gebietsschema.  
  
 Weitere Informationen finden Sie unter [Format Specification Syntax: printf and wprintf Functions (Syntax der Formatangabe: printf- und wprintf-Funktionen)](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md).  
  
## <a name="return-value"></a>Rückgabewert  
 Die Anzahl geschriebener Zeichen oder ein negativer Wert im Falle eines Ausgabefehlers. Wenn `format` ein NULL-Zeiger ist, wird der Handler für ungültige Parameter wie unter [Parameter Validation (Parameterüberprüfung)](../../c-runtime-library/parameter-validation.md) beschrieben aufgerufen. Wenn die weitere Ausführung zugelassen wird, wird `errno` auf `EINVAL` festgelegt und – 1 zurückgegeben.  
  
## <a name="remarks"></a>Hinweise  
 Jede dieser Funktionen verwendet einen Zeiger auf eine Argumentliste und verwendet dann die `_putch` Funktion, um die angegebenen Daten in die Konsole zu formatieren und zu schreiben. (`_vcwprintf_p` verwendet `_putwch` anstelle von `_putch`. `_vcwprintf_p` ist die Breitzeichenversion von `_vcprintf_p`. Eine Zeichenfolge mit Breitzeichen wird als Argument akzeptiert.)  
  
 Die Versionen dieser Funktionen mit dem `_l`-Suffix sind beinahe identisch, verwenden jedoch den Gebietsschemaparameter, der anstelle des aktuellen Gebietsschemas übergeben wurde.  
  
 Jedes `argument` (falls vorhanden) wird entsprechend der jeweiligen Formatangabe in `format` konvertiert und ausgegeben. Die Formatangabe unterstützt positionelle Parameter, damit Sie die Reihenfolge, in der die Argumente verwendet werden, in der Formatzeichenfolge angeben können. Weitere Informationen finden Sie unter [printf_p Positional Parameters (printf_p-Positionsparameter)](../../c-runtime-library/printf-p-positional-parameters.md).  
  
 Diese Funktionen übersetzen keine Zeilenvorschubzeichen in Carriage Return-Zeilenvorschub (CR-LF) Kombinationen bei der Ausgabe.   
  
> [!IMPORTANT]
>  Stellen Sie sicher, dass `format` keine benutzerdefinierte Zeichenfolge ist. Weitere Informationen finden Sie unter [Vermeiden von Pufferüberläufen](http://msdn.microsoft.com/library/windows/desktop/ms717795).  
  
 Diese Funktionen überprüfen den Eingabezeiger und die Formatzeichenfolge. Wenn `format` oder `argument` `NULL` sind, oder wenn die Formatzeichenfolge ungültige Formatierungszeichen enthält, rufen diese Funktionen den Handler für ungültige Parameter auf, wie unter [Parameter Validation (Parameterüberprüfung)](../../c-runtime-library/parameter-validation.md) beschrieben. Wenn die weitere Ausführung zugelassen wird, geben diese Funktionen "– 1" zurück und legen `errno` auf `EINVAL`fest.  
  
### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen  
  
|Tchar.h-Routine|_UNICODE und _MBCS nicht definiert|_MBCS definiert|_UNICODE definiert|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_vtcprintf_p`|`_vcprintf_p`|`_vcprintf_p`|`_vcwprintf_p`|  
|`_vtcprintf_p_l`|`_vcprintf_p_l`|`_vcprintf_p_l`|`_vcwprintf_p_l`|  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------|  
|`_vcprintf_p`, `_vcprintf_p_l`|\<conio.h> and \<stdarg.h>|  
|`_vcwprintf_p`, `_vcwprintf_p_l`|\<conio.h> and \<stdarg.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Beispiel  
  
```  
// crt_vcprintf_p.c  
// compile with: /c  
#include <conio.h>  
#include <stdarg.h>  
  
// An error formatting function that's used to print to the console.  
int eprintf(const char* format, ...)  
{  
   va_list args;  
   va_start(args, format);  
   int result = _vcprintf_p(format, args);  
   va_end(args);  
   return result;
}  
  
int main()  
{  
   int n = eprintf("parameter 2 = %2$d; parameter 1 = %1$s\r\n",  
      "one", 222);  
   _cprintf_s("%d characters printed\r\n");  
}  
```  
  
```Output  
parameter 2 = 222; parameter 1 = one  
38 characters printed  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Console and Port I/O (Konsole und Port-E/A)](../../c-runtime-library/console-and-port-i-o.md)   
 [_cprintf, _cprintf_l, _cwprintf, _cwprintf_l](../../c-runtime-library/reference/cprintf-cprintf-l-cwprintf-cwprintf-l.md)   
 [va_arg, va_copy, va_end, va_start](../../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md)   
 [printf_p Positional Parameters (printf_p-Positionsparameter)](../../c-runtime-library/printf-p-positional-parameters.md)