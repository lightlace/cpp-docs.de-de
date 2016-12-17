---
title: "_getdcwd, _wgetdcwd"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
apiname: 
  - "_getdcwd"
  - "_wgetdcwd"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
  - "api-ms-win-crt-stdio-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "wgetdcwd"
  - "getdcwd"
  - "_getdcwd"
  - "tgetdcwd"
  - "_wgetdcwd"
  - "_tgetdcwd"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "wgetdcwd-Funktion"
  - "Arbeitsverzeichnis"
  - "getdcwd-Funktion"
  - "_getdcwd-Funktion"
  - "_wgetdcwd-Funktion"
  - "Aktuelles Arbeitsverzeichnis"
  - "Verzeichnisse [C++], aktuelle Arbeit"
ms.assetid: 184152f5-c7b0-495b-918d-f9a6adc178bd
caps.latest.revision: 24
caps.handback.revision: "24"
ms.author: "corob"
manager: "ghogen"
---
# _getdcwd, _wgetdcwd
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ruft den vollständigen Pfad des aktuellen Arbeitsverzeichnisses auf dem angegebenen Laufwerk ab.  
  
## Syntax  
  
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
  
#### Parameter  
 `drive`  
 Eine nicht negative ganze Zahl, die das Laufwerk angibt \(0 \= Standardlaufwerk, 1 \= A, 2 \= B usw.\).  
  
 Wenn das angegebene Laufwerk nicht verfügbar ist oder die Art des Laufwerks \(z. B. Wechseldatenträger, festes Laufwerk, CD\-ROM\-Laufwerk, RAM\-Datenträger oder Netzlaufwerk\) nicht bestimmt werden kann, wird der Handler für ungültige Parameter aufgerufen, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben.  
  
 `buffer`  
 Speicherort für den Pfad oder **NULL**.  
  
 Wenn **NULL** angegeben ist, wird diese Funktion weist einen Puffer mit mindestens `maxlen` Größe mit **Malloc**, und der Rückgabewert der `_getdcwd` ist ein Zeiger auf den zugeordneten Puffer. Der Puffer kann freigegeben werden, indem `free` aufgerufen und der Zeiger übergeben wird.  
  
 `maxlen`  
 Eine positive ganze Zahl ungleich Null, die die maximale Länge des Pfads angibt, in Zeichen: `char` für `_getdcwd` und `wchar_t` für `_wgetdcwd`.  
  
 Wenn `maxlen` nicht größer als Null ist, wird der Handler für ungültige Parameter aufgerufen, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben.  
  
## Rückgabewert  
 Zeiger auf eine Zeichenfolge, die den vollständigen Pfad des aktuellen Arbeitsverzeichnisses auf dem angegebenen Laufwerk darstellt, oder `NULL`, wodurch ein Fehler angegeben wird.  
  
 Wenn `buffer` als `NULL` angegeben ist und nicht genügend Arbeitsspeicher zum Zuweisen von `maxlen`\-Zeichen vorhanden ist, tritt ein Fehler auf und `errno` wird auf `ENOMEM` festgelegt. Wenn die Länge des Pfads, der das abschließende Nullzeichen enthält, `maxlen` überschreitet, tritt ein Fehler auf und `errno` wird auf `ERANGE` festgelegt. Weitere Informationen zu diesen Fehlercodes finden Sie unter [errno, \_doserrno, \_sys\_errlist und \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## Hinweise  
 Die `_getdcwd`\-Funktion ruft den vollständigen Pfad des aktuellen Arbeitsverzeichnisses auf dem angegebenen Laufwerk ab und speichert ihn unter `buffer`. Wenn das aktuelle Arbeitsverzeichnis auf das Stammverzeichnis festgelegt ist, endet die Zeichenfolge mit einem umgekehrten Schrägstrich \(\\\). Wenn das aktuelle Arbeitsverzeichnis nicht auf das Stammverzeichnis festgelegt ist, endet die Zeichenfolge mit dem Namen des Verzeichnisses und nicht mit einem umgekehrten Schrägstrich.  
  
 `_wgetdcwd` ist eine Breitzeichenversion von `_getdcwd`, und der `buffer`\-Parameter und der Rückgabewert sind Zeichenfolgen mit Breitzeichen. Andernfalls verhalten sich `_wgetdcwd` und `_getdcwd` identisch.  
  
 Diese Funktion ist threadsicher, obwohl er abhängt **GetFullPathName**, selbst nicht threadsicher. Allerdings können Sie Threadsicherheit verletzen, wenn die Multithreadanwendung sowohl diese Funktion aufruft und **GetFullPathName**. Weitere Informationen finden Sie unter [MSDN Library](http://go.microsoft.com/fwlink/?LinkID=150542) und suchen Sie nach **GetFullPathName**.  
  
 Die Version dieser Funktion, die über das `_nolock`\-Suffix verfügt, ist mit dieser Funktion identisch, allerdings ist sie nicht threadsicher und nicht vor Störungen durch andere Threads geschützt. Weitere Informationen finden Sie unter [\_getdcwd\_nolock, \_wgetdcwd\_nolock](../../c-runtime-library/reference/getdcwd-nolock-wgetdcwd-nolock.md).  
  
 Wenn `_DEBUG` und `_CRTDBG_MAP_ALLOC` definiert werden, werden Aufrufe von `_getdcwd` und `_wgetdcwd` durch Aufrufe von `_getdcwd_dbg` und `_wgetdcwd_dbg` ersetzt, sodass Sie Speicherbelegungen debuggen können. Weitere Informationen finden Sie unter [\_getdcwd\_dbg, \_wgetdcwd\_dbg](../../c-runtime-library/reference/getdcwd-dbg-wgetdcwd-dbg.md)  
  
### Zuordnung generischer Textroutinen  
  
|Tchar.h\-Routine|\_UNICODE und \_MBCS nicht definiert|\_MBCS definiert|\_UNICODE definiert|  
|----------------------|------------------------------------------|----------------------|-------------------------|  
|`_tgetdcwd`|`_getdcwd`|`_getdcwd`|`_wgetdcwd`|  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_getdcwd`|\<direct.h\>|  
|`_wgetdcwd`|\<direct.h\> oder \<wchar.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## Beispiel  
 Siehe das Beispiel in [\_getdrive](../../c-runtime-library/reference/getdrive.md).  
  
## .NET Framework-Entsprechung  
 [System::Environment::CurrentDirectory](https://msdn.microsoft.com/en-us/library/system.environment.currentdirectory.aspx)  
  
## Siehe auch  
 [Verzeichnissteuerung](../../c-runtime-library/directory-control.md)   
 [\_chdir, \_wchdir](../../c-runtime-library/reference/chdir-wchdir.md)   
 [\_getcwd, \_wgetcwd](../../c-runtime-library/reference/getcwd-wgetcwd.md)   
 [\_getdrive](../../c-runtime-library/reference/getdrive.md)   
 [\_mkdir, \_wmkdir](../../c-runtime-library/reference/mkdir-wmkdir.md)   
 [\_rmdir, \_wrmdir](../../c-runtime-library/reference/rmdir-wrmdir.md)