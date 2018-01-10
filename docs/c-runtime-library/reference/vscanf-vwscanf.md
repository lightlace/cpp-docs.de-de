---
title: vscanf, vwscanf | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- vscanf
- vwscanf
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
- vscanf
- vwscanf
- _vtscanf
dev_langs: C++
ms.assetid: d1df595b-11bc-4682-9441-a92616301e3b
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 21f7a0061f5a06482763279bd005f3cc7fa575f3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="vscanf-vwscanf"></a>vscanf, vwscanf
Liest formatierte Daten aus dem Standardeingabestream. Sicherere Versionen dieser Funktion sind verfügbar. Informationen dazu finden Sie unter [vscanf_s, vwscanf_s](../../c-runtime-library/reference/vscanf-s-vwscanf-s.md).  
  
## <a name="syntax"></a>Syntax  
  
```  
int vscanf(  
   const char *format,  
   va_list arglist  
);  
int vwscanf(  
   const wchar_t *format,  
   va_list arglist  
);  
  
```  
  
#### <a name="parameters"></a>Parameter  
 `format`  
 Formatsteuerzeichenfolge.  
  
 `arglist`  
 Variablenargumentenliste.  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt die Anzahl von Feldern zurück, die erfolgreich konvertiert und zugewiesen wurden. Der Rückgabewert umfasst keine Felder, die gelesen, aber nicht zugewiesen wurden. Ein Rückgabewert von 0 gibt an, dass keine Felder zugewiesen wurden.  
  
 Wenn `format` ein `NULL`-Zeiger ist, wird der Handler für ungültige Parameter, wie unter [Parameter Validation (Parameterüberprüfung)](../../c-runtime-library/parameter-validation.md) beschrieben, aufgerufen. Wenn die weitere Ausführung zugelassen wird, geben diese Funktionen `EOF` zurück und stellen `errno` auf `EINVAL` ein.  
  
 Weitere Informationen zu diesen und anderen Fehlercodes finden Sie unter [errno, _doserrno, _sys_errlist, and _sys_nerr (errno, _doserrno, _sys_errlist und _sys_nerr)](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Hinweise  
 Die `vscanf`-Funktion liest Daten aus dem Standardeingabestream `stdin` und schreibt die Daten in die Speicherorte, die durch die `arglist`-Argumentliste angegeben werden. Jedes Argument in der Liste muss ein Zeiger auf einen Variablentyp sein, der einem Typspezifizierer in `format` entspricht. Wenn der Kopiervorgang zwischen Zeichenfolgen ausgeführt wird, die sich überschneiden, ist das Verhalten nicht definiert.  
  
> [!IMPORTANT]
>  Wenn Sie `vscanf` verwenden, um eine Zeichenfolge zu lesen, müssen Sie immer einer Breite für das `%s`-Format angeben (beispielsweise `"%32s"` anstelle von `"%s"`). Anderenfalls kann eine falsch formatierte Eingabe zu einem Pufferüberlauf führen. Alternativ können Sie auch [vscanf_s, vwscanf_s](../../c-runtime-library/reference/vscanf-s-vwscanf-s.md) oder [fgets](../../c-runtime-library/reference/fgets-fgetws.md) verwenden.  
  
 `vwscanf` ist eine Breitzeichenversion von `vscanf`. Das `format`-Argument für `vwscanf` ist eine Breitzeichenfolge. `vwscanf` und `vscanf` verhalten sich identisch, wenn der Stream in ANSI-Modus geöffnet ist. `vscanf` unterstützt nicht die Eingabe aus einem UNICODE-Stream.  
  
### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen  
  
|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_vtscanf`|`vscanf`|`vscanf`|`vwscanf`|  
  
 Weitere Informationen finden Sie unter [Format Specification Fields: scanf and wscanf Functions (Formatspezifikationsfelder: Funktionen scanf und wscanf)](../../c-runtime-library/format-specification-fields-scanf-and-wscanf-functions.md).  
  
## <a name="requirements"></a>Anforderungen  
  
|-Routine zurückgegebener Wert|Erforderlicher Header|  
|-------------|---------------------|  
|`vscanf`|\<stdio.h>|  
|`vwscanf`|\<stdio.h> oder \<wchar.h>|  
  
 Die Konsole wird in [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)]-Apps nicht unterstützt. Die mit der Konsole verknüpften Standardstreamhandles, `stdin`, `stdout` und `stderr`, müssen umgeleitet werden, bevor sie von C-Laufzeitfunktionen in [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)]-Apps verwendet werden können. Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Beispiel  
  
```  
// crt_vscanf.c  
// compile with: /W3  
// This program uses the vscanf and vwscanf functions  
// to read formatted input.  
  
#include <stdio.h>  
#include <stdarg.h>  
  
int call_vscanf(char *format, ...)  
{  
    int result;  
    va_list arglist;  
    va_start(arglist, format);  
    result = vscanf(format, arglist);  
    va_end(arglist);  
    return result;  
}  
  
int call_vwscanf(wchar_t *format, ...)  
{  
    int result;  
    va_list arglist;  
    va_start(arglist, format);  
    result = vwscanf(format, arglist);  
    va_end(arglist);  
    return result;  
}  
  
int main( void )  
{  
    int   i, result;  
    float fp;  
    char  c, s[81];  
    wchar_t wc, ws[81];  
    result = call_vscanf( "%d %f %c %C %80s %80S", &i, &fp, &c, &wc, s, ws );  
    printf( "The number of fields input is %d\n", result );  
    printf( "The contents are: %d %f %c %C %s %S\n", i, fp, c, wc, s, ws);  
    result = call_vwscanf( L"%d %f %hc %lc %80S %80ls", &i, &fp, &c, &wc, s, ws );  
    wprintf( L"The number of fields input is %d\n", result );  
    wprintf( L"The contents are: %d %f %C %c %hs %s\n", i, fp, c, wc, s, ws);  
}  
  
```  
  
```Output  
  
      71 98.6 h z Byte characters  
36 92.3 y n Wide charactersThe number of fields input is 6  
The contents are: 71 98.599998 h z Byte characters  
The number of fields input is 6  
The contents are: 36 92.300003 y n Wide characters  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Floating-Point Support (Gleitkommaunterstützung)](../../c-runtime-library/floating-point-support.md)   
 [Stream I/O (Stream-E/A)](../../c-runtime-library/stream-i-o.md)   
 [Gebietsschema](../../c-runtime-library/locale.md)   
 [fscanf, _fscanf_l, fwscanf, _fwscanf_l](../../c-runtime-library/reference/fscanf-fscanf-l-fwscanf-fwscanf-l.md)   
 [printf, _printf_l, wprintf, _wprintf_l](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)   
 [sprintf, _sprintf_l, swprintf, _swprintf_l, \__swprintf_l](../../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)   
 [sscanf, _sscanf_l, swscanf, _swscanf_l](../../c-runtime-library/reference/sscanf-sscanf-l-swscanf-swscanf-l.md)   
 [vscanf_s, vwscanf_s](../../c-runtime-library/reference/vscanf-s-vwscanf-s.md)