---
title: _write | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _write
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
- _write
dev_langs:
- C++
helpviewer_keywords:
- _write function
- write function
- files [C++], writing to
ms.assetid: 7b868c33-766f-4e1a-95a7-e8d25f0604c4
caps.latest.revision: 21
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
ms.openlocfilehash: 9e6e654e043a71cbb6eb75c53077b14400b82d72
ms.contentlocale: de-de
ms.lasthandoff: 04/01/2017

---
# <a name="write"></a>_write
Schreibt Daten in eine Datei.  
  
## <a name="syntax"></a>Syntax  
  
```  
int _write(  
   int fd,  
   const void *buffer,  
   unsigned int count   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `fd`  
 Dateideskriptor der Datei, in die die Daten geschrieben werden.  
  
 `buffer`  
 Zu schreibende Daten.  
  
 `count`  
 Anzahl der Bytes.  
  
## <a name="return-value"></a>Rückgabewert  
 Im Erfolgsfall gibt `_write` die Anzahl der tatsächlich geschriebenen Bytes zurück. Wenn der auf der Festplatte verbleibende Speicherplatz geringer ist als die Größe des Puffers, versucht die Funktion, auf die Festplatte zu schreiben, und `_write` schlägt fehl und leert keine Inhalte des Puffers auf die Festplatte. Ein Rückgabewert von – 1 zeigt einen Fehler. Wenn ungültige Parameter übergeben werden, ruft diese Funktion den Handler für ungültige Parameter auf, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben. Wenn die weitere Ausführung zugelassen wird, gibt die Funktion -1 zurück, und `errno` wird auf einen von drei Werten gesetzt: `EBADF` mit der Bedeutung, dass der Dateideskriptor ungültig ist oder die Datei nicht zum Schreiben geöffnet wird; `ENOSPC` mit der Bedeutung, dass auf dem Gerät nicht mehr genug Speicherplatz für den Vorgang vorhanden ist, oder `EINVAL` mit der Bedeutung, dass `buffer` ein NULL-Zeiger war oder dass im Unicode-Modus eine ungerade `count` von Bytes zum Schreiben in eine Datei übergeben wurde.  
  
 Weitere Informationen zu diesen und anderen Rückgabecodes finden Sie unter [errno, _doserrno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
 Wenn die Datei im Textmodus geöffnet wird, wird jeder Zeilenvorschub durch einen Wagenrücklauf - Zeilenvorschub in der Ausgabe ersetzt. Diese Ersetzung hat keine Auswirkung auf den Rückgabewert.  
  
 Wenn die Datei in einem Unicode-Übersetzungsmodus geöffnet wird – z.B., wenn `fd` durch Verwendung von `_open` oder `_sopen` und eines Modusparameters geöffnet wird, der `_O_WTEXT`, `_O_U16TEXT` oder `_O_U8TEXT` enthält, oder wenn sie durch Verwendung von `fopen` und eines Modusparameters geöffnet wird, der `ccs=UNICODE`, `ccs=UTF-16LE` oder `ccs=UTF-8` enthält, oder wenn der Modus durch Verwendung von `_setmode` in einen Unicode-Übersetzungsmodus geändert wird, wird `buffer` als Zeiger auf ein Array von `wchar_t` interpretiert, das **UTF-16**-Daten enthält. Der Versuch, in diesem Modus eine ungerade Anzahl von Bytes zu schreiben, führt zu einem Parametervalidierungsfehler.  
  
## <a name="remarks"></a>Hinweise  
 Die `_write`-Funktion schreibt `count` Bytes aus dem `buffer` in die mit `fd` verknüpfte Datei. Der Schreibvorgang beginnt an der aktuellen Position des Dateizeigers (falls vorhanden) für die betreffende Datei. Wenn die Datei zum Anhängen geöffnet ist, beginnt der Vorgang am aktuellen Dateiende. Nach dem Schreibvorgang wird der Dateizeiger um die Anzahl der tatsächlich geschriebenen Bytes erhöht.  
  
 Beim Schreiben in Dateien, die im Textmodus geöffnet wurden, behandelt `_write` ein STRG+Z-Zeichen als logisches Dateiende. Beim Schreiben auf ein Gerät behandelt `_write` ein STRG+Zeichen im Puffer als Ausgabeabschlusszeichen.  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------|  
|`_write`|\<io.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Beispiel  
  
```  
// crt__write.c  
//   
// This program opens a file for output and uses _write to write  
// some bytes to the file.  
  
#include <io.h>  
#include <stdio.h>  
#include <stdlib.h>  
#include <fcntl.h>  
#include <sys/types.h>  
#include <sys/stat.h>  
#include <errno.h>  
#include <share.h>  
  
char buffer[] = "This is a test of '_write' function";  
  
int main( void )  
{  
   int         fileHandle = 0;  
   unsigned    bytesWritten = 0;  
  
   if ( _sopen_s(&fileHandle, "write.o", _O_RDWR | _O_CREAT,  
                  _SH_DENYNO, _S_IREAD | _S_IWRITE) )  
      return -1;  
  
   if (( bytesWritten = _write( fileHandle, buffer, sizeof( buffer ))) == -1 )  
   {  
      switch(errno)  
      {  
         case EBADF:  
            perror("Bad file descriptor!");  
            break;  
         case ENOSPC:  
            perror("No space left on device!");  
            break;  
         case EINVAL:  
            perror("Invalid parameter: buffer was NULL!");  
            break;  
         default:  
            // An unrelated error occured   
            perror("Unexpected error!");  
      }  
   }  
   else  
   {  
      printf_s( "Wrote %u bytes to file.\n", bytesWritten );  
   }  
   _close( fileHandle );  
}  
```  
  
```Output  
Wrote 36 bytes to file.  
```  
  
## <a name="see-also"></a>Siehe auch  
 [E/A auf niedriger Ebene](../../c-runtime-library/low-level-i-o.md)   
 [fwrite](../../c-runtime-library/reference/fwrite.md)   
 [_open, _wopen](../../c-runtime-library/reference/open-wopen.md)   
 [_read](../../c-runtime-library/reference/read.md)   
 [_setmode](../../c-runtime-library/reference/setmode.md)
