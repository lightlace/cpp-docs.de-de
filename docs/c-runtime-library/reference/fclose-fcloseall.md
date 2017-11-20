---
title: fclose, _fcloseall | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- fclose
- _fcloseall
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
- fclose
- _fcloseall
dev_langs: C++
helpviewer_keywords:
- fclose function
- streams, closing
- _fcloseall function
ms.assetid: c3c6ea72-92c6-450a-a33e-3e568d2784a4
caps.latest.revision: "17"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: d0cb985b4e2ddeea853ccd40668a3e378834e68a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="fclose-fcloseall"></a>fclose, _fcloseall
Schließt einen Stream (`fclose`) oder schließt alle geöffneten Streams (`_fcloseall`).  
  
## <a name="syntax"></a>Syntax  
  
```  
int fclose(   
   FILE *stream   
);  
int _fcloseall( void );  
```  
  
#### <a name="parameters"></a>Parameter  
 `stream`  
 Zeiger zur `FILE` -Struktur.  
  
## <a name="return-value"></a>Rückgabewert  
 `fclose` gibt 0 zurück, wenn der Stream erfolgreich geschlossen wurde. `_fcloseall` gibt die Gesamtanzahl der geschlossenen Streams zurück. Beide Funktionen geben bei einem Fehler `EOF` zurück.  
  
## <a name="remarks"></a>Hinweise  
 Die `fclose`-Funktion schließt `stream`. Wenn `stream` `NULL` ist, wird der ungültige Parameterhandler aufgerufen, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben. Wenn die weitere Ausführung zugelassen wird, legt `fclose` `errno` auf `EINVAL` fest, und gibt `EOF` zurück. Es wird empfohlen, den `stream`-Zeiger vor Aufruf dieser Funktion stets zu überprüfen.  
  
 Weitere Informationen zu diesen und anderen Fehlercodes finden Sie unter [_doserrno, errno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
 Die `_fcloseall`-Funktion schließt alle geöffneten Streams bis auf `stdin`, `stdout`, `stderr` (und in MS-DOS `_stdaux` und `_stdprn`). Außerdem werden alle von `tmpfile` erstellten Dateien geschlossen und gelöscht. Bei beiden Funktionen werden alle Puffer, die dem Stream zugewiesen sind, vor dem Schließen geleert. Systemseitig angegebene Puffer werden freigegeben, wenn der Stream geschlossen wird. Vom Benutzer durch `setbuf` und `setvbuf` zugewiesene Puffer werden nicht automatisch freigegeben.  
  
 **Hinweis:** Wenn diese Funktionen verwendet werden, um einen Stream zu schließen, werden ebenso wie der Stream auch der zugrundeliegende Dateideskriptor und das Dateihandle des Betriebssystems geschlossen. Rufen Sie daher nicht `_close` zusätzlich auf, um den Dateideskriptor zu schließen, wenn die Datei ursprünglich als Dateihandle oder Dateideskriptor geöffnet wurde und mit `fclose` geschlossen wurde; rufen Sie auch keine Win32-Funktion `CloseHandle` auf, um das Dateihandle zu schließen.  
  
 `fclose` und `_fcloseall` enthalten Code zum Schutz von Störungen durch andere Threads. Informationen zu nicht sperrenden Versionen von `fclose` finden Sie unter `_fclose_nolock`.  
  
## <a name="requirements"></a>Anforderungen  
  
|Funktion|Erforderlicher Header|  
|--------------|---------------------|  
|`fclose`|\<stdio.h>|  
|`_fcloseall`|\<stdio.h>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="example"></a>Beispiel  
 Ein Beispiel hierfür finden Sie unter [open](../../c-runtime-library/reference/fopen-wfopen.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Stream-E/A](../../c-runtime-library/stream-i-o.md)   
 [_close](../../c-runtime-library/reference/close.md)   
 [_fdopen, _wfdopen](../../c-runtime-library/reference/fdopen-wfdopen.md)   
 [fflush](../../c-runtime-library/reference/fflush.md)   
 [fopen, _wfopen](../../c-runtime-library/reference/fopen-wfopen.md)   
 [freopen, _wfreopen](../../c-runtime-library/reference/freopen-wfreopen.md)