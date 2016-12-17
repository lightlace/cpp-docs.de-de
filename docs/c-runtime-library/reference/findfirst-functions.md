---
title: "_findfirst, _findfirst32, _findfirst32i64, _findfirst64, _findfirst64i32, _findfirsti64, _wfindfirst, _wfindfirst32, _wfindfirst32i64, _wfindfirst64, _wfindfirst64i32, _wfindfirsti64"
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
  - "_findfirst"
  - "_wfindfirst"
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
  - "api-ms-win-crt-filesystem-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "findfirst32i64"
  - "wfindfirst32i64"
  - "tfindfirst64"
  - "_findfirst64i32"
  - "_wfindfirst32i64"
  - "_wfindfirsti64"
  - "wfindfirst"
  - "_tfindfirsti64"
  - "findfirst32"
  - "_tfindfirst32"
  - "_findfirsti64"
  - "findfirst"
  - "wfindfirst64"
  - "wfindfirst32"
  - "tfindfirst32"
  - "_wfindfirst64i32"
  - "findfirst64i32"
  - "tfindfirst64i32"
  - "_wfindfirst"
  - "findfirsti64"
  - "_findfirst32i64"
  - "wfindfirst64i32"
  - "_wfindfirst32"
  - "_findfirst32"
  - "_tfindfirst32i64"
  - "tfindfirst"
  - "_tfindfirst64i32"
  - "findfirst64"
  - "_tfindfirst"
  - "_findfirst64"
  - "_tfindfirst64"
  - "tfindfirst32i64"
  - "_findfirst"
  - "_wfindfirst64"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_tfindfirst64-Funktion"
  - "_wfindfirst64i32-Funktion"
  - "_wfindfirst32i64-Funktion"
  - "wfindfirst32-Funktion"
  - "_findfirst-Funktion"
  - "wfindfirst64-Funktion"
  - "_wfindfirst-Funktion"
  - "_findfirst64i32-Funktion"
  - "wfindfirst-Funktion"
  - "_findfirst64-Funktion"
  - "tfindfirst32-Funktion"
  - "_tfindfirst64i32-Funktion"
  - "findfirst-Funktion"
  - "findfirst32i64-Funktion"
  - "tfindfirst64-Funktion"
  - "_tfindfirst32-Funktion"
  - "tfindfirst32i64-Funktion"
  - "tfindfirst64i32-Funktion"
  - "_wfindfirsti64-Funktion"
  - "_findfirst32i64-Funktion"
  - "findfirst32-Funktion"
  - "findfirsti64-Funktion"
  - "findfirst64i32-Funktion"
  - "tfindfirsti64-Funktion"
  - "tfindfirst-Funktion"
  - "_wfindfirst32-Funktion"
  - "wfindfirsti64-Funktion"
  - "_tfindfirsti64-Funktion"
  - "_tfindfirst-Funktion"
  - "_tfindfirst32i64-Funktion"
  - "findfirst64-Funktion"
  - "_findfirst32-Funktion"
  - "_findfirsti64-Funktion"
  - "wfindfirst32i64-Funktion"
  - "wfindfirst64i32-Funktion"
  - "_wfindfirst64-Funktion"
ms.assetid: 9bb46d1a-b946-47de-845a-a0b109a33ead
caps.latest.revision: 25
caps.handback.revision: "23"
ms.author: "corob"
manager: "ghogen"
---
# _findfirst, _findfirst32, _findfirst32i64, _findfirst64, _findfirst64i32, _findfirsti64, _wfindfirst, _wfindfirst32, _wfindfirst32i64, _wfindfirst64, _wfindfirst64i32, _wfindfirsti64
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Stellen Sie Informationen zur ersten Instanz eines Dateinamens bereit, die der Datei entspricht, die im `filespec`\-Argument angegeben wird.  
  
## Syntax  
  
```  
intptr_t _findfirst(  
   const char *filespec,  
   struct _finddata_t *fileinfo   
);  
intptr_t _findfirst32(  
   const char *filespec,  
   struct _finddata32_t *fileinfo   
);  
intptr_t _findfirst64(  
   const char *filespec,  
   struct _finddata64_t *fileinfo   
);  
intptr_t _findfirsti64(  
   const char *filespec,  
   struct _finddatai64_t *fileinfo   
);  
intptr_t _findfirst32i64(  
   const char *filespec,  
   struct _finddata32i64_t *fileinfo   
);  
intptr_t _findfirst64i32(  
   const char *filespec,  
   struct _finddata64i32_t *fileinfo   
);  
intptr_t _wfindfirst(  
   const wchar_t *filespec,  
   struct _wfinddata_t *fileinfo   
);  
intptr_t _wfindfirst32(  
   const wchar_t *filespec,  
   struct _wfinddata32_t *fileinfo   
);  
intptr_t _wfindfirst64(  
   const wchar_t *filespec,  
   struct _wfinddata64_t *fileinfo   
);  
intptr_t _wfindfirsti64(  
   const wchar_t *filespec,  
   struct _wfinddatai64_t *fileinfo   
);  
intptr_t _wfindfirst32i64(  
   const wchar_t *filespec,  
   struct _wfinddata32i64_t *fileinfo   
);  
intptr_t _wfindfirst64i32(  
   const wchar_t *filespec,  
   struct _wfinddata64i32_t *fileinfo   
);  
```  
  
#### Parameter  
 `filespec`  
 Zieldateispezifikation \(kann Platzhalterzeichen einschließen\).  
  
 `fileinfo`  
 Dateiinformationspuffer.  
  
## Rückgabewert  
 Wenn erfolgreich, gibt `_findfirst` einen eindeutigen Suchenhandle zurück, das die Datei oder die Gruppe aus Dateien angibt, die die `filespec` \- Spezifikation übereinstimmen, die in einem abschließenden Aufruf an [\_findnext](../../c-runtime-library/reference/findnext-functions.md) oder `_findclose` verwendet werden kann.  Andernfalls wird `_findfirst` \- 1 zurück und legt `errno` auf einen der folgenden Werte fest.  
  
 `EINVAL`  
 Ungültiger Parameter: `filespec` oder `fileinfo` festgelegt wäre `NULL`.  Oder, das Betriebssystem hat einen unerwarteten Fehler zurück.  
  
 `ENOENT`  
 Dateibeschreibung, die nicht gefunden werden konnte.  
  
 `ENOMEM`  
 Nicht genügend Arbeitsspeicher.  
  
 `EINVAL`  
 Ungültige Dateinamenangaben oder Dateiname, der angegeben wurde, war größer als `MAX_PATH`.  
  
 Weitere Informationen zu diesen und anderen Rückgabecodes finden Sie unter [\_doserrno, errno, \_sys\_errlist und \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
 Wenn ein ungültiger Parameter übergeben wird, rufen diese Funktionen den ungültigen Parameterhandler auf, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben.  
  
## Hinweise  
 Sie müssen [\_findclose](../../c-runtime-library/reference/findclose.md) aufrufen, nachdem Sie entweder mit `_findfirst` oder `_findnext`\-Funktion beendet wurde \(oder alle Varianten\).  Dies gibt die Ressourcen frei, die durch diese Funktionen in der Anwendung verwendet werden.  
  
 Die Variationen dieser Funktionen, die das `w` \- Präfix haben, sind Breitzeichenversionen; andernfalls sind sie zu den entsprechenden Einzelbytefunktionen identisch.  
  
 Varianten der 32\-Bit\- oder 64\-Bit\-Zeit dieser Funktionen Stützgibt und der 32\-Bit\- oder 64\-Bit\-Dateigrößen ein.  Das erste numerische Suffix \(`32` oder `64`\) gibt die Größe des Zeittyps an; das zweite Suffix ist entweder `i32` oder `i64` und gibt an, ob die Dateigröße als 32\-Bit\- oder 64\-Bit\-ganze Zahl dargestellt wird.  Informationen darüber, welche Versionen 32\-Bit\- und 64\-Bit\-Zeittypen und \-Dateigrößen unterstützen, finden Sie die folgende Tabelle.  Das Suffix `i32` oder `i64` wird weggelassen, wenn sie identisch ist, der die Größe des Zeittyps, sodass `_findfirst64` auch 64\-Bit\-Dateilängen unterstützt und `_findfirst32` nur 32\-Bit\-Dateilängen unterstützt.  
  
 Diese unterschiedlichen Formen der Funktionsverwendung der Struktur `_finddata_t` für den `fileinfo`\-Parameter.  Weitere Informationen zur Struktur, finden Sie unter [Dateinamen\-Suchfunktionen](../../c-runtime-library/filename-search-functions.md).  
  
 Die Variationen, die einen 64\-Bit\-Zeittyp verwenden, aktivieren bis 23:59 die oben angegeben werden können, DateiErstellungsdatumsangaben: 59 3000 am 31. Dezember, UTC.  Die, die 32\-Bit\-Zeittypen verwenden, stellen Datumsangaben nur bis 19:14 dar: Am 7. Januar 18 2038, UTC.  Mitternacht am 1. Januar 1970 ist die untere Begrenzung des Zeitraums für alle diese Funktionen.  
  
 Sofern, dass Sie einen bestimmten Grund haben, die Versionen verwenden, die der Zeitgröße explizit angeben, wird mit `_findfirst` oder `_wfindfirst` oder, wenn Sie Unterstützungsdateigrößen größer als 3 GB benötigen, `_findfirsti64` oder `_wfindfirsti64`.  Alle diese Funktionen verwenden den 64\-Bit\-Zeittyp.  In früheren Versionen wurde diese Funktionen einen 32\-Bit\-Zeittyp.  Wenn dies eine Änderung für eine Anwendung ist, können Sie `_USE_32BIT_TIME_T`, um das alte Verhalten wiederherzustellen.  Wenn `_USE_32BIT_TIME_T` definiert wurde, verwenden `_findfirst`, `_finfirsti64` und ihre entsprechenden Unicode\-Versionen eine 32\-Bit\-Zeit.  
  
### Die Zeit Typs fest und fügen Sie Längen\-Typ\-Variationen von \_findfirst  
  
|Funktionen|`_USE_32BIT_TIME_T` definiert?|Zeittyp|Dateilängentyp|  
|----------------|------------------------------------|-------------|--------------------|  
|`_findfirst`, `_wfindfirst`|Nicht definiert|64 Bit|32 Bit|  
|`_findfirst`, `_wfindfirst`|Definiert|32 Bit|32 Bit|  
|`_findfirst32`, `_wfindfirst32`|Beeinflusst weder von der Makrodefinition|32 Bit|32 Bit|  
|`_findfirst64`, `_wfindfirst64`|Beeinflusst weder von der Makrodefinition|64 Bit|64 Bit|  
|`_findfirsti64`, `_wfindfirsti64`|Nicht definiert|64 Bit|64 Bit|  
|`_findfirsti64`, `_wfindfirsti64`|Definiert|32 Bit|64 Bit|  
|`_findfirst32i64`, `_wfindfirst32i64`|Beeinflusst weder von der Makrodefinition|32 Bit|64 Bit|  
|`_findfirst64i32`, `_wfindfirst64i32`|Beeinflusst weder von der Makrodefinition|64 Bit|32 Bit|  
  
### Zuordnung generischer Textroutinen  
  
|Tchar.h\-Routine|\_UNICODE und \_MBCS nicht definiert|\_MBCS definiert|\_UNICODE definiert|  
|----------------------|------------------------------------------|----------------------|-------------------------|  
|`_tfindfirst`|`_findfirst`|`_findfirst`|`_wfindfirst`|  
|`_tfindfirst32`|`_findfirst32`|`_findfirst32`|`_wfindfirst32`|  
|`_tfindfirst64`|`_findfirst64`|`_findfirst64`|`_wfindfirst64`|  
|`_tfindfirsti64`|`_findfirsti64`|`_findfirsti64`|`_wfindfirsti64`|  
|`_tfindfirst32i64`|`_findfirst32i64`|`_findfirst32i64`|`_wfindfirst32i64`|  
|`_tfindfirst64i32`|`_findfirst64i32`|`_findfirst64i32`|`_wfindfirst64i32`|  
  
## Anforderungen  
  
|Funktion|Erforderlicher Header|  
|--------------|---------------------------|  
|`_findfirst`|\<io.h\>|  
|`_findfirst32`|\<io.h\>|  
|`_findfirst64`|\<io.h\>|  
|`_findfirsti64`|\<io.h\>|  
|`_findfirst32i64`|\<io.h\>|  
|`_findfirst64i32`|\<io.h\>|  
|`_wfindfirst`|\<io.h oder\> wchar.h \<\>|  
|`_wfindfirst32`|\<io.h oder\> wchar.h \<\>|  
|`_wfindfirst64`|\<io.h oder\> wchar.h \<\>|  
|`_wfindfirsti64`|\<io.h oder\> wchar.h \<\>|  
|`_wfindfirst32i64`|\<io.h oder\> wchar.h \<\>|  
|`_wfindfirst64i32`|\<io.h oder\> wchar.h \<\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## .NET Framework-Entsprechung  
 [System::IO::DirectoryInfo::GetFiles](https://msdn.microsoft.com/en-us/library/system.io.directoryinfo.getfiles.aspx)  
  
## Siehe auch  
 [Systemaufrufe](../../c-runtime-library/system-calls.md)   
 [Dateinamen\-Suchfunktionen](../../c-runtime-library/filename-search-functions.md)