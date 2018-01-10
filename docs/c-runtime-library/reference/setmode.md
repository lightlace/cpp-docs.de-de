---
title: _setmode | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _setmode
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
f1_keywords: _setmode
dev_langs: C++
helpviewer_keywords:
- Unicode [C++], console output
- files [C++], modes
- _setmode function
- file translation [C++], setting mode
- files [C++], translation
- setmode function
ms.assetid: 996ff7cb-11d1-43f4-9810-f6097182642a
caps.latest.revision: "23"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c01c76deb32962236673e7aa16c76fedc13cdc45
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="setmode"></a>_setmode
Legt den Dateiübersetzungsmodus fest.  
  
## <a name="syntax"></a>Syntax  
  
```  
int _setmode (  
   int fd,  
   int mode   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `fd`  
 Dateideskriptor.  
  
 `mode`  
 Neuer Übersetzungsmodus.  
  
## <a name="return-value"></a>Rückgabewert  
 Im Erfolgsfall wird der vorherige Übersetzungsmodus zurückgegeben.  
  
 Wenn ungültige Parameter an die Funktion übergeben werden, wird der Handler für ungültige Parameter aufgerufen, wie in [Parameter Validation (Parameterüberprüfung)](../../c-runtime-library/parameter-validation.md)beschrieben. Wenn die weitere Ausführung zugelassen wird, gibt diese Funktion gibt-1 zurück und setzt `errno` entweder `EBADF`, wodurch einen Ungültiger Dateideskriptor oder `EINVAL`, wodurch ein ungültiges `mode` Argument.  
  
 Weitere Informationen zu diesen und anderen Rückgabecodes finden Sie unter [_doserrno, errno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Hinweise  
 Die Funktion `_setmode` setzt den Übersetzungsmodus der von `mode` bereitgestellten Datei auf `fd`. Durch die Übergabe von `_O_TEXT` als `mode` wird der Modus für den übersetzten Text festgelegt. Carriage Return Line feed (CR-LF) Kombinationen werden in ein einzelnes Zeilenvorschubzeichen bei Eingabe übersetzt. Zeilenvorschubzeichen werden bei der Ausgabe in Kombinationen aus Wagenrücklauf und Zeilenvorschub (CR-LF) übersetzt. Durch die Übergabe von `_O_BINARY` wird der binäre (nicht übersetzte) Modus festgelegt, in dem diese Übersetzungen unterdrückt werden.  
  
 Sie können auch übergeben `_O_U16TEXT`, `_O_U8TEXT`, oder `_O_WTEXT` Unicode-Modus zu aktivieren, wie im zweiten Beispiel weiter unten in diesem Dokument veranschaulicht. `_setmode` wird normalerweise verwendet, um den Standardübersetzungsmodus von `stdin` und `stdout` zu ändern, aber Sie können es für jede Datei verwenden. Wenn Sie `_setmode` auf den Dateideskriptor für einen Stream anwenden, rufen Sie `_setmode` auf, bevor Sie Eingabe- oder Ausgabevorgänge an diesem Stream durchführen.  
  
> [!CAUTION]
>  Wenn Sie Daten in einen Dateienstream schreiben, leeren Sie den Code explizit, indem Sie [fflush](../../c-runtime-library/reference/fflush.md) verwenden, bevor Sie mit `_setmode` den Modus ändern. Wenn Sie den Code nicht leeren, kann es zu unerwartetem Verhalten kommen. Wenn Sie keine Daten in den Stream geschrieben haben, müssen Sie den Code nicht leeren.  
  
## <a name="requirements"></a>Anforderungen  
  
|-Routine zurückgegebener Wert|Erforderlicher Header|Optionale Header|  
|-------------|---------------------|----------------------|  
|`_setmode`|\<io.h>|\<fcntl.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Beispiel  
  
```  
// crt_setmode.c  
// This program uses _setmode to change  
// stdin from text mode to binary mode.  
  
#include <stdio.h>  
#include <fcntl.h>  
#include <io.h>  
  
int main( void )  
{  
   int result;  
  
   // Set "stdin" to have binary mode:  
   result = _setmode( _fileno( stdin ), _O_BINARY );  
   if( result == -1 )  
      perror( "Cannot set mode" );  
   else  
      printf( "'stdin' successfully changed to binary mode\n" );  
}  
```  
  
```Output  
'stdin' successfully changed to binary mode  
```  
  
## <a name="example"></a>Beispiel  
  
```  
// crt_setmodeunicode.c  
// This program uses _setmode to change  
// stdout to Unicode. Cyrillic and Ideographic  
// characters will appear on the console (if  
// your console font supports those character sets).  
  
#include <fcntl.h>  
#include <io.h>  
#include <stdio.h>  
  
int main(void) {  
    _setmode(_fileno(stdout), _O_U16TEXT);  
    wprintf(L"\x043a\x043e\x0448\x043a\x0430 \x65e5\x672c\x56fd\n");  
    return 0;  
}  
```  
  
## <a name="see-also"></a>Siehe auch  
 [File Handling (Dateibehandlung)](../../c-runtime-library/file-handling.md)   
 [_creat, _wcreat](../../c-runtime-library/reference/creat-wcreat.md)   
 [fopen, _wfopen](../../c-runtime-library/reference/fopen-wfopen.md)   
 [_open, _wopen](../../c-runtime-library/reference/open-wopen.md)   
 [_set_fmode](../../c-runtime-library/reference/set-fmode.md)