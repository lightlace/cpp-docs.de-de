---
title: "_strdate_s, _wstrdate_s"
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
  - "_strdate_s"
  - "_wstrdate_s"
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
  - "api-ms-win-crt-time-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_strdate_s"
  - "wstrdate_s"
  - "_wstrdate_s"
  - "strdate_s"
  - "_tstrdate_s"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "Daten, Kopieren"
  - "tstrdate_s-Funktion"
  - "wstrdate_s-Funktion"
  - "_tstrdate_s-Funktion"
  - "strdate_s-Funktion"
  - "Kopieren von Daten"
  - "_strdate_s-Funktion"
  - "_wstrdate_s-Funktion"
ms.assetid: d41d8ea9-e5ce-40d4-864e-1ac29b455991
caps.latest.revision: 24
caps.handback.revision: "24"
ms.author: "corob"
manager: "ghogen"
---
# _strdate_s, _wstrdate_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Kopieren Sie das aktuelle Systemdatum in einem Puffer.  Diese Versionen sind von [\_strdate, \_wstrdate](../../c-runtime-library/reference/strdate-wstrdate.md) mit werden, wie in [Sicherheitsfunktionen in der CRT](../../c-runtime-library/security-features-in-the-crt.md) beschrieben.  
  
## Syntax  
  
```  
errno_t _strdate_s(  
   char *buffer,  
   size_t numberOfElements  
);  
errno_t _wstrdate_s(  
   wchar_t *buffer,  
   size_t numberOfElements  
);  
template <size_t size>  
errno_t _strdate_s(  
   char (&buffer)[size]  
); // C++ only  
template <size_t size>  
errno_t _wstrdate_s(  
   wchar_t (&buffer)[size]  
); // C++ only  
```  
  
#### Parameter  
 \[out\] `buffer`  
 Ein Zeiger auf einen Puffer, der der formatierte Datumszeichenfolge gefüllt wird.  
  
 \[in\] `numberOfElements`  
 Größe des Puffers.  
  
## Rückgabewert  
 Null wenn erfolgreich.  Der Rückgabewert ist ein Fehlercode, wenn ein Fehler auftritt.  Fehlercodes werden in ERRNO.H definiert; finden Sie folgenden Tabelle sind die genauen Fehler, die von dieser Funktion generiert werden.  Weitere Informationen zu Fehlercodes, finden Sie unter [errno](../../c-runtime-library/errno-constants.md).  
  
## Fehlerbedingungen  
  
|`buffer`|`numberOfElements`|Return|Inhalt von `buffer`|  
|--------------|------------------------|------------|-------------------------|  
|`NULL`|\(alle\)|`EINVAL`|Nicht geändert|  
|Nicht `NULL` \(Zeiger auf gültigen Puffer\)|0|`EINVAL`|Nicht geändert|  
|Nicht `NULL` \(Zeiger auf gültigen Puffer\)|0 \< `numberOfElements` \< 9|`EINVAL`|Leere Zeichenfolge|  
|Nicht `NULL` \(Zeiger auf gültigen Puffer\)|`numberOfElements` \>\= 9|0|Aktuelles Datum formatiert, wie in den Hinweisen angegeben|  
  
## Sicherheitsprobleme  
 Die Übergabe in einen nicht ungültigen Wert `NULL` für den Puffer ergibt eine Zugriffsverletzung, wenn der `numberOfElements`\-Parameter größer als 9. ist.  
  
 Das Übergeben von Werten für Größe, die größer ist, als das Originalgröße `buffer` ergibt Pufferüberlauf.  
  
## Hinweise  
 Diese Funktionen stellen sicherere Versionen von `_strdate` und `_wstrdate`.  Die Funktion `_strdate_s` kopiert das aktuelle Systemdatum dem Puffer, auf den durch `buffer`, formatiertes `mm`\/`dd`\/`yy` gezeigt wird, wobei `mm` zwei Ziffern ist, die den Monat darstellen, ist `dd` zwei Ziffern, die den Tag darstellen, und `yy` ist die letzten beiden Stellen des Jahrs.  Beispielsweise stellt die Zeichenfolge `12/05/99` am 5. Dezember 1999 dar.  Der Puffer muss 9 Zeichen lang sein.  
  
 `_wstrdate_s` ist eine Breitzeichenversion von `_strdate_s`. Das Argument und der Rückgabewert von `_wstrdate_s` sind Zeichenfolgen mit Breitzeichen.  Anderenfalls verhalten sich diese Funktionen identisch.  
  
 Wenn `buffer` ein `NULL` Zeiger ist oder wenn `numberOfElements` kleiner als 9 Zeichen ist, der ungültige Parameterhandler aufgerufen, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben.  Wenn die Ausführung zulässig ist, um fortzufahren, geben diese Funktionen festgelegtem \-1 und `errno` zu `EINVAL`, wenn der Puffer `NULL` ist, oder wenn `numberOfElements` kleiner oder gleich 0 ist, oder `errno` im Satz zu `ERANGE` zurück, wenn `numberOfElements` kleiner als 9 ist.  
  
 In C\+\+ wird die Verwendung dieser Funktionen durch Vorlagenüberladungen vereinfacht; die Überladungen können automatisch Rückschlüsse auf die Pufferlänge ziehen \(wodurch kein Größenargument mehr angegeben werden muss\), und sie können automatisch die älteren, nicht sicheren Funktionen durch ihre neueren, sicheren Entsprechungen ersetzen.  Weitere Informationen finden Sie unter [Sichere Vorlagenüberladungen](../../c-runtime-library/secure-template-overloads.md).  
  
### Zuordnung generischer Textroutinen:  
  
|TCHAR.H\-Routine|\_UNICODE & \_MBCS nicht definiert|\_MBCS definiert|\_UNICODE definiert|  
|----------------------|----------------------------------------|----------------------|-------------------------|  
|`_tstrdate_s`|`_strdate_s`|`_strdate_s`|`_wstrdate_s`|  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_strdate`|\<time.h\>|  
|`_wstrdate`|\<time.h oder\> wchar.h \<\>|  
|`_strdate_s`|\<time.h\>|  
  
## Beispiel  
 Im Beispiel für [time](../../c-runtime-library/reference/time-time32-time64.md).  
  
## .NET Framework-Entsprechung  
 [System::DateTime::Parse](https://msdn.microsoft.com/en-us/library/system.datetime.parse.aspx)  
  
## Siehe auch  
 [Uhrzeitverwaltung](../../c-runtime-library/time-management.md)   
 [asctime\_s, \_wasctime\_s](../../c-runtime-library/reference/asctime-s-wasctime-s.md)   
 [ctime\_s, \_ctime32\_s, \_ctime64\_s, \_wctime\_s, \_wctime32\_s, \_wctime64\_s](../../c-runtime-library/reference/ctime-s-ctime32-s-ctime64-s-wctime-s-wctime32-s-wctime64-s.md)   
 [gmtime\_s, \_gmtime32\_s, \_gmtime64\_s](../../c-runtime-library/reference/gmtime-s-gmtime32-s-gmtime64-s.md)   
 [localtime\_s, \_localtime32\_s, \_localtime64\_s](../../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md)   
 [mktime, \_mktime32, \_mktime64](../../c-runtime-library/reference/mktime-mktime32-mktime64.md)   
 [time, \_time32, \_time64](../../c-runtime-library/reference/time-time32-time64.md)   
 [\_tzset](../../c-runtime-library/reference/tzset.md)