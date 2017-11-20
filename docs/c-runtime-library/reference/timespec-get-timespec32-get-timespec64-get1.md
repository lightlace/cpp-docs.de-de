---
title: "Timespec_get, _timespec32_get, _timespec64_get1 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "cpp"
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "timespec_get"
  - "_timespec32_get"
  - "_timespec64_get"
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
  - "timespec_get"
  - "_timespec32_get"
  - "_timespec64_get"
  - "time/timespec_get"
  - "time/_timespec32_get"
  - "time/_timespec64_get"
  - "timespec"
  - "_timespec32"
  - "_timespec64"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "timespec_get-Funktion"
  - "_timespec32_get-Funktion"
  - "_timespec64_get-Funktion"
ms.assetid: ed757258-b4f2-4c1d-a91b-22ea6ffce4ab
caps.latest.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 4
---
# timespec_get, _timespec32_get, _timespec64_get
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Legt das Intervall, auf das das erste Argument verweist, auf die aktuelle Kalenderzeit fest, basierend auf der angegebenen Zeitbasis.  
  
## Syntax  
  
```  
int timespec_get(  
    struct timespec* const time_spec,  
    int const base  
);  
int _timespec32_get(  
    struct _timespec32* const time_spec,  
    int const base  
);  
int _timespec64_get(  
    struct _timespec64* const time_spec,  
    int const base  
);  
  
```  
  
#### Parameter  
 `time_spec`  
 Zeiger auf eine Struktur, die auf die seit dem Beginn der Epoche verstrichene Zeit in Sekunden und Nanosekunden festgelegt ist.  
  
 `base`  
 Ein implementierungsspezifischer Wert ungleich null, der die Zeitbasis angibt.  
  
## Rückgabewert  
 Der Wert von `base` im Erfolgsfall, andernfalls wird null zurückgegeben.  
  
## Hinweise  
 Die `timespec_get`\-Funktionen legen die aktuelle Zeit in der Struktur fest, auf die das `time_spec`\-Argument verweist. Alle Versionen dieser Struktur besitzen zwei Member, `tv_sec` und `tv_nsec`. Der `tv_sec`\-Wert ist auf die ganze Anzahl der Sekunden, und `tv_nsec` auf ganzzahlige Nanosekunden festgelegt, auf die Auflösung der Systemuhr gerundet, seit dem durch `base` angegebenen Beginn der Epoche.  
  
 **Microsoft\-spezifisch**  
  
 Diese Funktionen unterstützen nur `TIME_UTC` als Wert von `base`. Dadurch wird der `time_spec`\-Wert auf die Anzahl Sekunden und Nanosekunden seit dem Beginn der Epoche,  1. Januar 1970 Mitternacht UTC \(koordinierte Weltzeit\) festgelegt. In einer `struct _timespec32` ist `tv_sec` ein `__time32_t`\-Wert. In einer `struct _timespec64` ist `tv_sec` ein `__time64_t`\-Wert. In einer `struct timespec` ist `tv_sec` ein `time_t`\-Typ, der eine Länge von 32 Bit oder 64 Bit aufweist, abhängig davon, ob das Präprozessormakro \_USE\_32BIT\_TIME\_T definiert ist. Die `timespec_get`\-Funktion ist eine Inlinefunktion, die `_timespec32_get` aufruft, falls \_USE\_32BIT\_TIME\_T definiert ist; andernfalls wird `_timespec64_get` aufgerufen.  
  
 **Ende Microsoft\-spezifisch**  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`timespec_get`, `_timespec32_get`, `_timespec64_get`|C: \<time.h\>, C\+\+: \<ctime\> oder \<time.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## Siehe auch  
 [Uhrzeitverwaltung](../../c-runtime-library/time-management.md)   
 [asctime, \_wasctime](../../c-runtime-library/reference/asctime-wasctime.md)   
 [asctime\_s, \_wasctime\_s](../../c-runtime-library/reference/asctime-s-wasctime-s.md)   
 [\_ftime, \_ftime32, \_ftime64](../../c-runtime-library/reference/ftime-ftime32-ftime64.md)   
 [gmtime, \_gmtime32, \_gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md)   
 [gmtime\_s, \_gmtime32\_s, \_gmtime64\_s](../../c-runtime-library/reference/gmtime-s-gmtime32-s-gmtime64-s.md)   
 [localtime, \_localtime32, \_localtime64](../../c-runtime-library/reference/localtime-localtime32-localtime64.md)   
 [localtime\_s, \_localtime32\_s, \_localtime64\_s](../../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md)   
 [time, \_time32, \_time64](../../c-runtime-library/reference/time-time32-time64.md)   
 [\_utime, \_utime32, \_utime64, \_wutime, \_wutime32, \_wutime64](../../c-runtime-library/reference/utime-utime32-utime64-wutime-wutime32-wutime64.md)