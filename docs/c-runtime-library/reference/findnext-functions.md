---
title: "_findnext, _findnext32, _findnext32i64, _findnext64, _findnext64i32, _findnexti64, _wfindnext, _wfindnext32, _wfindnext32i64, _wfindnext64, _wfindnext64i32, _wfindnexti64"
ms.custom: na
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
apiname: 
  - "_wfindnext"
  - "_findnext"
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
  - "findnext"
  - "_wfindnext32i64"
  - "_tfindnext64i32"
  - "findnext32"
  - "findnext32i64"
  - "wfindnext64i32"
  - "_wfindnext"
  - "tfindnext64"
  - "findnexti64"
  - "_findnexti64"
  - "_tfindnexti64"
  - "_findnext64i32"
  - "tfindnexti64"
  - "tfindnext32"
  - "_wfindnext64i32"
  - "findnext64i32"
  - "_findnext"
  - "_tfindnext32i64"
  - "_wfindnext64"
  - "wfindnext"
  - "wfindnext32"
  - "tfindnext32i64"
  - "_findnext64"
  - "_tfindnext64"
  - "_wfindnext32"
  - "findnext64"
  - "_findnext32i64"
  - "tfindnext"
  - "wfindnexti64"
  - "tfindnext64i32"
  - "_tfindnext32"
  - "wfindnext32i64"
  - "wfindnext64"
  - "_wfindnexti64"
  - "_tfindnext"
  - "_findnext32"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_wfindnexti64-Funktion"
  - "_tfindnext32-Funktion"
  - "wfindnexti64-Funktion"
  - "_wfindnext32i64-Funktion"
  - "findnext32i64-Funktion"
  - "tfindnext64i32-Funktion"
  - "_tfindnext64i32-Funktion"
  - "_findnext-Funktion"
  - "findnext64i32-Funktion"
  - "_tfindnext-Funktion"
  - "findnext32-Funktion"
  - "tfindnext32-Funktion"
  - "_findnext32-Funktion"
  - "_tfindnext32i64-Funktion"
  - "_wfindnext-Funktion"
  - "tfindnext-Funktion"
  - "_findnext64-Funktion"
  - "findnext64-Funktion"
  - "_findnext64i32-Funktion"
  - "wfindnext32i64-Funktion"
  - "findnext-Funktion"
  - "wfindnext32-Funktion"
  - "_wfindnext64i32-Funktion"
  - "findnexti64-Funktion"
  - "_wfindnext64-Funktion"
  - "_findnext32i64-Funktion"
  - "_findnexti64-Funktion"
  - "_tfindnext64-Funktion"
  - "wfindnext64i32-Funktion"
  - "tfindnexti64-Funktion"
  - "wfindnext64-Funktion"
  - "wfindnext-Funktion"
  - "tfindnext64-Funktion"
  - "_wfindnext32-Funktion"
  - "tfindnext32i64-Funktion"
  - "_tfindnexti64-Funktion"
ms.assetid: 75d97188-5add-4698-a46c-4c492378f0f8
caps.latest.revision: 17
caps.handback.revision: "15"
ms.author: "corob"
manager: "ghogen"
---
# _findnext, _findnext32, _findnext32i64, _findnext64, _findnext64i32, _findnexti64, _wfindnext, _wfindnext32, _wfindnext32i64, _wfindnext64, _wfindnext64i32, _wfindnexti64
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Suchen Sie den folgenden Namen ggf. der das `filespec`\-Argument in einem vorherigen Aufruf an [\_findfirst](../../c-runtime-library/reference/findfirst-functions.md) entspricht, und ändern Sie dann den `fileinfo`\-Strukturinhalt entsprechend.  
  
## Syntax  
  
```  
int _findnext(  
   intptr_t handle,  
   struct _finddata_t *fileinfo   
);  
int _findnext32(  
   intptr_t handle,  
   struct _finddata32_t *fileinfo   
);  
int _findnext64(  
   intptr_t handle,  
   struct __finddata64_t *fileinfo   
);  
int _findnexti64(  
   intptr_t handle,  
   struct __finddatai64_t *fileinfo   
);  
int _findnext32i64(  
   intptr_t handle,  
   struct _finddata32i64_t *fileinfo   
);  
int _findnext64i32(  
   intptr_t handle,  
   struct _finddata64i32_t *fileinfo   
);  
int _wfindnext(  
   intptr_t handle,  
   struct _wfinddata_t *fileinfo   
);  
int _wfindnext32(  
   intptr_t handle,  
   struct _wfinddata32_t *fileinfo   
);  
int _wfindnext64(  
   intptr_t handle,  
   struct _wfinddata64_t *fileinfo   
);  
int _wfindnexti64(  
   intptr_t handle,  
   struct _wfinddatai64_t *fileinfo   
);  
int _wfindnext32i64(  
   intptr_t handle,  
   struct _wfinddatai64_t *fileinfo   
);  
int _wfindnext64i32(  
   intptr_t handle,  
   struct _wfinddata64i32_t *fileinfo   
);  
```  
  
#### Parameter  
 `handle`  
 Suchen Sie das Handle, das bei einem vorherigen Aufruf von `_findfirst` zurückgegeben wird.  
  
 `fileinfo`  
 Dateiinformationspuffer.  
  
## Rückgabewert  
 Wenn erfolgreich, gibt 0 zurück.  Andernfalls gibt \- 1 und legt `errno` auf einen Wert, der die Art des Fehlers angibt.  Mögliche Fehlercodes werden in der folgenden Tabelle dargestellt.  
  
 `EINVAL`  
 Ungültiger Parameter: `fileinfo` war `NULL`.  Oder, das Betriebssystem hat einen unerwarteten Fehler zurück.  
  
 `ENOENT`  
 Nicht mehr entsprechende Dateien gefunden werden können.  
  
 `ENOMEM`  
 Nicht genügend Speicher oder die Länge von Dateinamen überschritten `MAX_PATH`.  
  
 Wenn ein ungültiger Parameter übergeben wird, rufen diese Funktionen den ungültigen Parameterhandler auf, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben.  
  
## Hinweise  
 Sie müssen [\_findclose](../../c-runtime-library/reference/findclose.md) aufrufen, nachdem Sie entweder mit `_findfirst` oder `_findnext`\-Funktion beendet wurde \(oder alle Varianten\).  Dies gibt es Ressourcen frei, die durch diese Funktionen in der Anwendung verwendet werden.  
  
 Die Variationen dieser Funktionen mit dem Präfix `w` sind Breitzeichenversionen; andernfalls sind sie zu den entsprechenden Einzelbytefunktionen identisch.  
  
 Varianten der 32\-Bit\- oder 64\-Bit\-Zeit dieser Funktionen Stützgibt und der 32\-Bit\- oder 64\-Bit\-Dateigrößen ein.  Das erste numerische Suffix \(`32` oder `64`\) gibt die Größe des verwendeten Zeittyps an; das zweite Suffix ist entweder `i32` oder `i64` angibt, ob die Dateigröße als 32\-Bit\- oder 64\-Bit\-ganzeZahl dargestellt wird.  Informationen darüber, welche Versionen 32\-Bit\- und 64\-Bit\-Zeittypen und \-Dateigrößen unterstützen, finden Sie die folgende Tabelle.  Die Variationen, die einen 64\-Bit\-Zeittyp verwenden, bieten bis 23:59 die oben angegeben werden können, DateiErstellungsdatumsangaben: 59 3000 am 31. Dezember, UTC; während die mithilfe der 32\-Bit\-Zeittypen nur Datumsangaben von 19:14 darstellen: Am 7. Januar 18 2038, UTC.  Mitternacht am 1. Januar 1970 ist die untere Begrenzung des Zeitraums für alle diese Funktionen.  
  
 Sofern, dass Sie einen bestimmten Grund haben, die Versionen verwenden, die der Zeitgröße explizit angeben, wird mit `_findnext` oder `_wfindnext` oder, wenn Sie Unterstützungsdateigrößen größer als 3 GB benötigen, `_findnexti64` oder `_wfindnexti64`.  Alle diese Funktionen verwenden den 64\-Bit\-Zeittyp.  In früheren Versionen wurde diese Funktionen einen 32\-Bit\-Zeittyp.  Wenn dies eine Änderung für eine Anwendung ist, können Sie `_USE_32BIT_TIME_T`, um das alte Verhalten abzurufen.  Wenn `_USE_32BIT_TIME_T` definiert wurde, verwenden `_findnext`, `_finnexti64` und ihre entsprechenden Unicode\-Versionen eine 32\-Bit\-Zeit.  
  
### Die Zeit Typs fest und fügen Sie Längen\-Typ\-Variationen von \_findnext  
  
|Funktionen|`_USE_32BIT_TIME_T` definiert?|Zeittyp|Dateilängentyp|  
|----------------|------------------------------------|-------------|--------------------|  
|`_findnext`, `_wfindnext`|Nicht definiert|64 Bit|32 Bit|  
|`_findnext`, `_wfindnext`|Definiert|32 Bit|32 Bit|  
|`_findnext32`, `_wfindnext32`|Beeinflusst weder von der Makrodefinition|32 Bit|32 Bit|  
|`_findnext64`, `_wfindnext64`|Beeinflusst weder von der Makrodefinition|64 Bit|64 Bit|  
|`_findnexti64`, `_wfindnexti64`|Nicht definiert|64 Bit|64 Bit|  
|`_findnexti64`, `_wfindnexti64`|Definiert|32 Bit|64 Bit|  
|`_findnext32i64`, `_wfindnext32i64`|Beeinflusst weder von der Makrodefinition|32 Bit|64 Bit|  
|`_findnext64i32`, `_wfindnext64i32`|Beeinflusst weder von der Makrodefinition|64 Bit|32 Bit|  
  
### Zuordnung generischer Textroutinen  
  
|Tchar.h\-Routine|\_UNICODE und \_MBCS nicht definiert|\_MBCS definiert|\_UNICODE definiert|  
|----------------------|------------------------------------------|----------------------|-------------------------|  
|`_tfindnext`|`_findnext`|`_findnext`|`_wfindnext`|  
|`_tfindnext32`|`_findnext32`|`_findnext32`|`_wfindnext32`|  
|`_tfindnext64`|`_findnext64`|`_findnext64`|`_wfindnext64`|  
|`_tfindnexti64`|`_findnexti64`|`_findnexti64`|`_wfindnexti64`|  
|`_tfindnext32i64`|`_findnext32i64`|`_findnext32i64`|`_wfindnext32i64`|  
|`_tfindnext64i32`|`_findnext64i32`|`_findnext64i32`|`_wfindnext64i32`|  
  
## Anforderungen  
  
|Funktion|Erforderlicher Header|  
|--------------|---------------------------|  
|`_findnext`|\<io.h\>|  
|`_findnext32`|\<io.h\>|  
|`_findnext64`|\<io.h\>|  
|`_findnexti64`|\<io.h\>|  
|`_findnext32i64`|\<io.h\>|  
|`_findnext64i32`|\<io.h\>|  
|`_wfindnext`|\<io.h oder\> wchar.h \<\>|  
|`_wfindnext32`|\<io.h oder\> wchar.h \<\>|  
|`_wfindnext64`|\<io.h oder\> wchar.h \<\>|  
|`_wfindnexti64`|\<io.h oder\> wchar.h \<\>|  
|`_wfindnext32i64`|\<io.h oder\> wchar.h \<\>|  
|`_wfindnext64i32`|\<io.h oder\> wchar.h \<\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Bibliotheken  
 Alle Versionen [C\-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).  
  
## .NET Framework-Entsprechung  
 Nicht zutreffend. Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).  
  
## Siehe auch  
 [Systemaufrufe](../../c-runtime-library/system-calls.md)   
 [Dateinamen\-Suchfunktionen](../../c-runtime-library/filename-search-functions.md)