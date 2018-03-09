---
title: vsprintf, _vsprintf_l, vswprintf, _vswprintf_l, __vswprintf_l | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _vswprintf_l
- _vsprintf_l
- vsprintf
- vswprintf
- __vswprintf_l
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
- vstprintf
- vswprintf
- _vstprintf
- vsprintf
- __vswprintf_l
- _vsprintf_l
- _vswprintf_l
- vswprintf_l
dev_langs:
- C++
helpviewer_keywords:
- __vswprintf_l function
- _vstprintf_l function
- formatted text
- vstprintf_l function
- _vswprintf_l function
- vsprintf_l function
- buffers, avoiding overruns
- buffer overruns
- vswprintf_l function
- buffers, buffer overruns
- vstprintf function
- _vsprintf_l function
- vswprintf function
- vsprintf function
- _vstprintf function
ms.assetid: b8ef1c0d-58f9-4a18-841a-f1a989e1c29b
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c9e236d7b880b2bcc5a66f8f2494990c6b420193
ms.sourcegitcommit: c770a343def04ae77522708387c3f7c470e49969
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/08/2018
---
# <a name="vsprintf-vsprintfl-vswprintf-vswprintfl-vswprintfl"></a>vsprintf, _vsprintf_l, vswprintf, _vswprintf_l, __vswprintf_l
Schreiben von formatierter Ausgabe mithilfe eines Zeigers, der auf eine Liste von Argumenten zeigt. Sicherere Versionen dieser Funktionen sind verfügbar. Informationen dazu finden Sie unter [vsprintf_s, _vsprintf_s_l, vswprintf_s, _vswprintf_s_l](../../c-runtime-library/reference/vsprintf-s-vsprintf-s-l-vswprintf-s-vswprintf-s-l.md).  
  
## <a name="syntax"></a>Syntax  
  
```  
int vsprintf(  
   char *buffer,  
   const char *format,  
   va_list argptr   
);   
int _vsprintf_l(  
   char *buffer,  
   const char *format,  
   locale_t locale,  
   va_list argptr   
);   
int vswprintf(  
   wchar_t *buffer,  
   size_t count,  
   const wchar_t *format,  
   va_list argptr   
);  
int _vswprintf_l(  
   wchar_t *buffer,  
   size_t count,  
   const wchar_t *format,  
   locale_t locale,  
   va_list argptr   
);  
int __vswprintf_l(  
   wchar_t *buffer,  
   const wchar_t *format,  
   locale_t locale,  
   va_list argptr   
);  
template <size_t size>  
int vsprintf(  
   char (&buffer)[size],  
   const char *format,  
   va_list argptr   
); // C++ only  
template <size_t size>  
int _vsprintf_l(  
   char (&buffer)[size],  
   const char *format,  
   locale_t locale,  
   va_list argptr   
); // C++ only  
template <size_t size>  
int vswprintf(  
   wchar_t (&buffer)[size],  
   const wchar_t *format,  
   va_list argptr   
); // C++ only  
template <size_t size>  
int _vswprintf_l(  
   wchar_t (&buffer)[size],  
   const wchar_t *format,  
   locale_t locale,  
   va_list argptr   
); // C++ only  
```  
  
#### <a name="parameters"></a>Parameter  
 `buffer`  
 Speicherort für die Ausgabe.  
  
 `count`  
 Maximale Anzahl, der in der `UNICODE`-Version dieser Funktion zu speichernde Zeichen.  
  
 `format`  
 Formatangabe.  
  
 `argptr`  
 Zeiger zur Liste der Argumente.  
  
 `locale`  
 Das zu verwendende Gebietsschema.  
  
## <a name="return-value"></a>Rückgabewert  
 `vsprintf` und `vswprintf` geben die Anzahl der geschriebenen Zeichen ohne das abschließende Nullzeichen zurück oder einen negativen Wert, wenn ein Ausgabefehler auftritt. Wenn `buffer` oder `format` ein NULL-Zeiger ist, rufen diese Funktionen den Handler für ungültige Parameter auf, wie unter [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben. Wenn die weitere Ausführung zugelassen wird, geben diese Funktionen "– 1" zurück und legen `errno` auf `EINVAL`fest.  
  
 Weitere Informationen über diese und andere Fehlercodes finden Sie unter [errno, _doserrno, _sys_errlist, and _sys_nerr (_doserrno, errno, _sys_errlist und _sys_nerr)](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Hinweise  
 Jede dieser Funktionen verwendet einen Zeiger auf eine Argumentliste und formatiert und schreibt dann die angegebenen Daten in den Speicher, auf den von `buffer` gezeigt wird.  
  
 Die Versionen dieser Funktionen mit dem `_l` -Suffix sind beinahe identisch, verwenden jedoch den ihnen übergebenen Gebietsschemaparameter anstelle des aktuellen Threadgebietsschemas.  
  
> [!IMPORTANT]
>  Mit `vsprintf`, gibt es keine Möglichkeit, die Anzahl der Zeichen begrenzen geschrieben wird, was bedeutet, dass Code mit dieser Funktion für Pufferüberläufe anfällig ist. Verwenden Sie stattdessen [_vsnprintf](../../c-runtime-library/reference/vsnprintf-vsnprintf-vsnprintf-l-vsnwprintf-vsnwprintf-l.md), oder rufen Sie [_vscprintf](../../c-runtime-library/reference/vscprintf-vscprintf-l-vscwprintf-vscwprintf-l.md) auf, um zu bestimmen, welche Puffergröße benötigt wird. Stellen Sie zudem sicher, dass `format` keine benutzerdefinierte Zeichenfolge ist. Weitere Informationen finden Sie unter [Vermeiden von Pufferüberläufen](http://msdn.microsoft.com/library/windows/desktop/ms717795).  
  
 `vswprintf` ist zum ISO-C-Standard konform. Dieser erfordert den zweiten Parameter `count` des `size_t`-Typs. Um das alte, nicht dem Standard entsprechende Verhalten zu erzwingen, definieren Sie `_CRT_NON_CONFORMING_SWPRINTFS.` Da das alte Verhalten möglicherweise in zukünftigen Versionen nicht mehr enthalten ist, sollte der Code so geändert werden, dass er das neue konforme Verhalten verwendet.  
  
 In C++ haben diese Funktionen Vorlagenüberladungen, mit denen die neueren, sicheren Entsprechungen dieser Funktionen aufgerufen werden. Weitere Informationen finden Sie unter [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md).  
  
### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen  
  
|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_vstprintf`|`vsprintf`|`vsprintf`|`vswprintf`|  
|`_vstprintf_l`|`_vsprintf_l`|`_vsprintf_l`|`_vswprintf_l`|  
  
## <a name="requirements"></a>Anforderungen  
  
|-Routine zurückgegebener Wert|Erforderlicher Header|Optionale Header|  
|-------------|---------------------|----------------------|  
|`vsprintf`, `_vsprintf_l`|\<stdio.h> und \<stdarg.h>|\<varargs.h>*|  
|`vswprintf`, `_vswprintf_l`|\<stdio.h> oder \<wchar.h> und \<stdarg.h>|\<varargs.h>*|  
  
 \* Benötigt für die Kompatibilität mit UNIX V.  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="example"></a>Beispiel  
  
```  
// crt_vsprintf.c  
// compile with: /W3  
// This program uses vsprintf to write to a buffer.  
// The size of the buffer is determined by _vscprintf.  
  
#include <stdlib.h>  
#include <stdio.h>  
#include <stdarg.h>  
  
void test( char * format, ... )  
{  
    va_list args;  
    int     len;  
    char    *buffer;  
  
    // retrieve the variable arguments  
    va_start( args, format );  
  
    len = _vscprintf( format, args ) // _vscprintf doesn't count  
                                + 1; // terminating '\0'  
  
    buffer = (char*)malloc( len * sizeof(char) );  
  
    vsprintf( buffer, format, args ); // C4996  
    // Note: vsprintf is deprecated; consider using vsprintf_s instead  
    puts( buffer );  
  
    free( buffer ); 
    va_end( args ); 
}  
  
int main( void )  
{  
   test( "%d %c %d", 123, '<', 456 );  
   test( "%s", "This is a string" );  
}  
```  
  
```Output  
123 < 456  
This is a string  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Stream-E/A](../../c-runtime-library/stream-i-o.md)   
 [vprintf Functions (vprintf-Funktionen)](../../c-runtime-library/vprintf-functions.md)   
 [Syntax der Formatangabe: printf- und wprintf-Funktionen](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md)   
 [fprintf, _fprintf_l, fwprintf, _fwprintf_l](../../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md)   
 [printf, _printf_l, wprintf, _wprintf_l](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)   
 [sprintf, _sprintf_l, swprintf, _swprintf_l, \__swprintf_l](../../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)   
 [va_arg, va_copy, va_end, va_start](../../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md)
