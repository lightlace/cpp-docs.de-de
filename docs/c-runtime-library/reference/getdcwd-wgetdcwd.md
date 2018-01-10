---
title: _getdcwd, _wgetdcwd | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _getdcwd
- _wgetdcwd
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
- wgetdcwd
- getdcwd
- _getdcwd
- tgetdcwd
- _wgetdcwd
- _tgetdcwd
dev_langs: C++
helpviewer_keywords:
- wgetdcwd function
- working directory
- getdcwd function
- _getdcwd function
- _wgetdcwd function
- current working directory
- directories [C++], current working
ms.assetid: 184152f5-c7b0-495b-918d-f9a6adc178bd
caps.latest.revision: "24"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e314db740322fc3d5e7df5aeb6bd7de747e77695
ms.sourcegitcommit: 54035dce0992ba5dce0323d67f86301f994ff3db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/03/2018
---
# <a name="getdcwd-wgetdcwd"></a>_getdcwd, _wgetdcwd
Ruft den vollständigen Pfad des aktuellen Arbeitsverzeichnisses auf dem angegebenen Laufwerk ab.  
  
## <a name="syntax"></a>Syntax  
  
```  
char *_getdcwd(   
   int drive,  
   char *buffer,  
   int maxlen   
);  
wchar_t *_wgetdcwd(   
   int drive,  
   wchar_t *buffer,  
   int maxlen   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `drive`  
 Eine nicht negative ganze Zahl, die das Laufwerk angibt (0 = Standardlaufwerk, 1 = A, 2 = B usw.).  
  
 Wenn das angegebene Laufwerk nicht verfügbar ist oder die Art des Laufwerks (z. B. Wechseldatenträger, festes Laufwerk, CD-ROM-Laufwerk, RAM-Datenträger oder Netzlaufwerk) nicht bestimmt werden kann, wird der Handler für ungültige Parameter aufgerufen, wie in [Parameter Validation](../../c-runtime-library/parameter-validation.md)beschrieben.  
  
 `buffer`  
 Speicherort für den Pfad, oder **NULL**.  
  
 Bei Angabe von **NULL** weist diese Funktion einen Puffer mit mindestens `maxlen` -Größe zu, indem **malloc**verwendet wird, und der Rückgabewert von `_getdcwd` ist ein Zeiger auf den zugeordneten Puffer. Der Puffer kann freigegeben werden, indem `free` aufgerufen und der Zeiger übergeben wird.  
  
 `maxlen`  
 Eine positive ganze Zahl ungleich Null, die die maximale Länge des Pfads angibt, in Zeichen: `char` für `_getdcwd` und `wchar_t` für `_wgetdcwd`.  
  
 Wenn `maxlen` nicht größer als null ist, wird der ungültige Parameterhandler aufgerufen, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben.  
  
## <a name="return-value"></a>Rückgabewert  
 Zeiger auf eine Zeichenfolge, die den vollständigen Pfad des aktuellen Arbeitsverzeichnisses auf dem angegebenen Laufwerk darstellt, oder `NULL`, wodurch ein Fehler angegeben wird.  
  
 Wenn `buffer` als `NULL` angegeben ist und nicht genügend Arbeitsspeicher zum Zuweisen von `maxlen` -Zeichen vorhanden ist, tritt ein Fehler auf und `errno` wird auf `ENOMEM`festgelegt. Wenn die Länge des Pfads, der das abschließende Nullzeichen enthält, `maxlen`überschreitet, tritt ein Fehler auf und `errno` wird auf `ERANGE`festgelegt. Weitere Informationen zu diesen Fehlercodes finden Sie unter [errno, _doserrno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Hinweise  
 Die `_getdcwd` -Funktion ruft den vollständigen Pfad des aktuellen Arbeitsverzeichnisses auf dem angegebenen Laufwerk ab und speichert ihn unter `buffer`. Wenn das aktuelle Arbeitsverzeichnis auf das Stammverzeichnis festgelegt ist, endet die Zeichenfolge mit einem umgekehrten Schrägstrich (\\). Wenn das aktuelle Arbeitsverzeichnis nicht auf das Stammverzeichnis festgelegt ist, endet die Zeichenfolge mit dem Namen des Verzeichnisses und nicht mit einem umgekehrten Schrägstrich.  
  
 `_wgetdcwd` ist eine Breitzeichenversion von `_getdcwd`, und der `buffer` -Parameter und der Rückgabewert sind Zeichenfolgen mit Breitzeichen. Andernfalls verhalten sich `_wgetdcwd` und `_getdcwd` identisch.  
  
 Diese Funktion ist threadsicher, obwohl sie von der Funktion **GetFullPathName**abhängig ist, die selbst nicht threadsicher ist. Es kann jedoch zu einer Verletzung der Threadsicherheit kommen, wenn die Multithreadanwendung sowohl diese Funktion als auch **GetFullPathName**aufruft. Weitere Informationen finden Sie in der [MSDN Library](http://go.microsoft.com/fwlink/p/?linkid=150542) . Suchen Sie dort nach **GetFullPathName**.  
  
 Die Version dieser Funktion, die über das `_nolock` -Suffix verfügt, ist mit dieser Funktion identisch, allerdings ist sie nicht threadsicher und nicht vor Störungen durch andere Threads geschützt. Weitere Informationen finden Sie unter [_getdcwd_nolock, _wgetdcwd_nolock](../../c-runtime-library/reference/getdcwd-nolock-wgetdcwd-nolock.md).  
  
 Wenn `_DEBUG` und `_CRTDBG_MAP_ALLOC` definiert werden, werden Aufrufe von `_getdcwd` und `_wgetdcwd` durch Aufrufe von `_getdcwd_dbg` und `_wgetdcwd_dbg` ersetzt, sodass Sie Speicherbelegungen debuggen können. Weitere Informationen finden Sie unter[_getdcwd_dbg, _wgetdcwd_dbg](../../c-runtime-library/reference/getdcwd-dbg-wgetdcwd-dbg.md)  
  
### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen  
  
|Tchar.h-Routine|_UNICODE und _MBCS nicht definiert|_MBCS definiert|_UNICODE definiert|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_tgetdcwd`|`_getdcwd`|`_getdcwd`|`_wgetdcwd`|  
  
## <a name="requirements"></a>Anforderungen  
  
|-Routine zurückgegebener Wert|Erforderlicher Header|  
|-------------|---------------------|  
|`_getdcwd`|\<direct.h>|  
|`_wgetdcwd`|\<direct.h> oder \<wchar.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Beispiel  
 Siehe das Beispiel in [_getdrive](../../c-runtime-library/reference/getdrive.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Directory Control (Verzeichnissteuerung)](../../c-runtime-library/directory-control.md)   
 [_chdir, _wchdir](../../c-runtime-library/reference/chdir-wchdir.md)   
 [_getcwd, _wgetcwd](../../c-runtime-library/reference/getcwd-wgetcwd.md)   
 [_getdrive](../../c-runtime-library/reference/getdrive.md)   
 [_mkdir, _wmkdir](../../c-runtime-library/reference/mkdir-wmkdir.md)   
 [_rmdir, _wrmdir](../../c-runtime-library/reference/rmdir-wrmdir.md)