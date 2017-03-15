---
title: "Standardtypen | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "__time64_t"
  - "_diskfree_t"
  - "_CRT_DUMP_CLIENT"
  - "_fsize_t"
  - "__timeb64"
  - "File"
  - "__utimeb64"
  - "jmp_buf"
  - "__finddata64_t"
  - "_wfinddata_t"
  - "_finddata_t"
  - "utimbuf64"
  - "wint_t"
  - "wctrans_t"
  - "wctype_t"
  - "_HFILE"
  - "_secerr_handler_func"
  - "clock_t"
  - "fpos_t"
  - "_dev_t"
  - "time64_t"
  - "wfinddata64_t"
  - "stat64"
  - "ldiv_t"
  - "_EXCEPTION_POINTERS"
  - "terminate_function"
  - "size_t"
  - "timeb64"
  - "tm"
  - "_HEAPINFO"
  - "unexpected_function"
  - "_CrtMemState"
  - "_se_translator_function"
  - "sig_atomic_t"
  - "_CRT_REPORT_HOOK"
  - "_complex"
  - "_w_finddatai64_t"
  - "_timeb"
  - "_onexit_t"
  - "_RTC_ErrorNumber"
  - "lconv"
  - "_PNH"
  - "_off_t"
  - "ptrdiff_t"
  - "time_t"
  - "_FPIEEE_RECORD"
  - "_exception"
  - "__w_finddata64_t"
  - "__stat64"
  - "_utimbuf"
  - "__utimbuf64"
  - "div_t"
  - "_CRT_ALLOC_HOOK"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__finddata64_t-Typ"
  - "__stat64-Typ"
  - "__time64_t-Typ"
  - "__timeb64-Typ"
  - "__utimbuf64-Typ"
  - "__wfinddata64_t-Typ"
  - "_complex-Typ"
  - "_CRT_ALLOC_HOOK-Typ"
  - "_CRT_DUMP_CLIENT-Typ"
  - "_CRT_REPORT_HOOK-Typ"
  - "_dev_t-Typ"
  - "_diskfree_t-Typ"
  - "_exception-Typ"
  - "_EXCEPTION_POINTERS-Typ"
  - "_finddata_t-Typ"
  - "_FPIEEE_RECORD-Typ"
  - "_fsize_t-Typ"
  - "_HEAPINFO-Typ"
  - "_HFILE-Typ"
  - "_locale_t-Typ"
  - "_off_t-Typ"
  - "_onexit_t-Typ"
  - "_PNH-Typ"
  - "_RTC_ErrorNumber-Typ"
  - "_se_translater_function-Typ"
  - "_secerr_handler_func-Typ"
  - "_stat-Typ"
  - "_timeb-Typ"
  - "_utimbuf-Typ"
  - "_wfinddata_t-Typ"
  - "_wfinddatai64_t-Typ"
  - "clock_t-Typ"
  - "Komplexe Typen"
  - "CRT, Standardtypen"
  - "CRT_ALLOC_HOOK-Typ"
  - "CRT_DUMP_CLIENT-Typ"
  - "CRT_REPORT_HOOK-Typ"
  - "CrtMemState-Typ"
  - "dev_t-Typ"
  - "diskfree_t-Typ"
  - "div_t-Typ"
  - "exception-Typ"
  - "EXCEPTION_POINTERS-Typ"
  - "FILE-Konstante"
  - "finddata_t-Typ"
  - "FPIEEE_RECORD-Typ"
  - "fpos_t-Typ"
  - "HEAPINFO-Typ"
  - "HFILE-Typ"
  - "intptr_t-Typ"
  - "jmp_buf-Typ"
  - "lconv-Typ"
  - "ldiv_t-Typ"
  - "off_t-Typ"
  - "onexit_t-Typ"
  - "PNH-Typ"
  - "ptrdiff_t-Typ"
  - "RTC_ErrorNumber-Typ"
  - "se_translater_function-Typ"
  - "secerr_handler_func-Typ"
  - "sig_atomic_t-Typ"
  - "size_t-Typ"
  - "stat-Typ"
  - "terminate_function-Typ"
  - "time_t-Typ"
  - "timeb-Typ"
  - "timeb64"
  - "tm-Typ"
  - "uintptr_t-Typ"
  - "unexpected_function-Typedef"
  - "utimbuf-Typ"
  - "va_list-Typ"
  - "wchar_t-Typ"
  - "wctrans_t-Typ"
  - "wctype_t-Typ"
  - "wfinddata_t-Typ"
  - "wfinddatai64_t-Typ"
  - "wint_t-Typ"
ms.assetid: 23312dd2-4a6a-4d70-9b48-2a5d0d8c9f28
caps.latest.revision: 27
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 27
---
# Standardtypen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Microsoft\-Laufzeitbibliothek definiert die folgenden Standardtypen und TypeDefs.  
  
### Ganzzahltypen mit fester Breite \(stdint.h\)  
  
|Name|Entsprechender integrierter Typ|  
|----------|-------------------------------------|  
|int8\_t, uint8\_t|signed char, unsigned char|  
|int16\_t, int16\_t|short, unsigned short|  
|int32\_t, uint32\_t|int, unsigned int|  
|int64\_t, int64\_t|long long, unsigned long long|  
|int\_least8\_t, uint\_least8\_t|signed char, unsigned char|  
|int\_least16\_t, uint\_least16\_t|short, unsigned short|  
|int\_least32\_t, uint\_least32\_t|int, unsigned int|  
|int\_least64\_t, uint\_least64\_t|long long, unsigned long long|  
|int\_fast8\_t, uint\_fast8\_t|signed char, unsigned char|  
|int\_fast16\_t, uint\_fast16\_t|int, unsigned int|  
|int\_fast32\_t, uint\_fast32\_t|int, unsigned int|  
|int\_fast64\_t, uint\_fast64\_t|long long, unsigned long long|  
|intmax\_t, uintmax\_t|long long, unsigned long long|  
  
|Typ|Beschreibung|Deklariert in|  
|---------|------------------|-------------------|  
|`clock_t` \(lang\)|Speichert Zeitwerte, die von [Uhr](../c-runtime-library/reference/clock.md) verwendet werden.|TIME.H|  
|`_complex`\-Struktur|Speicher tatsächliche und imaginäre Teile komplexer Zahlen, die von [\_cabs](../c-runtime-library/reference/cabs.md) verwendet werden.|MATH.H|  
|`_CRT_ALLOC_HOOK`|Eine Typendefinition für die benutzerdefinierte Hookfunktion.  Wird in [\_CrtSetAllocHook](../c-runtime-library/reference/crtsetallochook.md) verwendet.|CRTDBG.H|  
|`_CRT_DUMP_CLIENT`,<br /><br /> `_CRT_DUMP_CLIENT_M`|Eine Typendefinition für eine Rückruffunktion, die in [\_CrtMemDumpAllObjectsSince](../c-runtime-library/reference/crtmemdumpallobjectssince.md) aufgerufen wird.|CRTDBG.H|  
|`_CrtMemState`\-Struktur|Stellt Informationen über den aktuellen Zustand des C\-Laufzeit\-Debugheaps bereit.|CRTDBG.H|  
|`_CRT_REPORT_HOOK`,<br /><br /> `_CRT_REPORT_HOOKW`,<br /><br /> `_CRT_REPORT_HOOKW_M`|Eine Typendefinition für eine Rückruffunktion, die in [\_CrtDbgReport](../c-runtime-library/reference/crtdbgreport-crtdbgreportw.md) aufgerufen wird.<br /><br /> Die Parameter für diese Funktion sind: Berichttyp, Ausgabenachricht und der Rückgabewert der Rückruffunktion.|CRTDBG.H|  
|`dev_t`, `_dev_t` kurze ganze Zahl oder ganze Zahl ohne Vorzeichen|Stellt Gerätehandles dar.|SYS\\TYPES.H|  
|`_diskfree_t` \-Struktur|Enthält Informationen über ein Laufwerk.  Wird von [\_getdiskfree](../c-runtime-library/reference/getdiskfree.md)**verwendet.**|DOS.H und DIRECT.H|  
|`div_t`\-, `ldiv_t`\- und `lldiv_t`\-Strukturen|Speichern Werte, die von [div](../c-runtime-library/reference/div.md), [ldiv](../c-runtime-library/reference/ldiv-lldiv.md) und [lldiv](../c-runtime-library/reference/ldiv-lldiv.md) zurückgegeben werden.|STDLIB.H|  
|`errno_t`\-Integer|Wird für einen Parameter oder einen Funktionsrückgabetyp verwendet, der Fehlercodes von `errno` behandelt.|STDDEF.H,<br /><br /> CRTDEFS.H|  
|`_exception`\-Struktur|Speichert Fehlerinformationen für [\_matherr](../c-runtime-library/reference/matherr.md).|MATH.H|  
|`_EXCEPTION_POINTERS`|Enthält einen Ausnahmedatensatz.  Weitere Informationen finden Sie unter [EXCEPTION\_POINTERS](http://msdn.microsoft.com/library/windows/desktop/ms679331).|FPIEEE.H|  
|`FILE` \-Struktur|Speichert Informationen zum aktuellen Zustand des Streams; wird in allen E\/A\-Operationen eines Streams verwendet.|STDIO.H|  
|`_finddata_t`\-, `_wfinddata_t`\-, `_finddata32_t`\-, `_wfinddata32_t`\-, `_finddatai64_t`\-, `_wfinddatai64_t`\-, `__finddata64_t`\-, `__wfinddata64_t`\-, `__finddata32i64_t`\-, `__wfinddata32i64_t`\-, `__finddata64i32_t`\-, `__wfinddata64i32_t`\-Strukturen|Speichert durch [\_findfirst, \_wfindfirst und verwandte Funktionen](../c-runtime-library/reference/findfirst-functions.md) und [\_findnext, \_wfindnext und verwandte Funktionen](../c-runtime-library/reference/findnext-functions.md) zurückgegebene Speicherdatei\-Attributinformationen.  Informationen über Strukturmember finden Sie unter [Dateinamen\-Suchfunktionen](../c-runtime-library/filename-search-functions.md).|IO.H, WCHAR.H|  
|`_FPIEEE_RECORD` \-Struktur|Enthält Informationen zur IEEE\-Gleitkommaausnahme; wird an einen benutzerfreundlichen Traphandler durch [\_fpieee\_flight](../c-runtime-library/reference/fpieee-flt.md) übergeben.|FPIEEE.H|  
|`fpos_t` \(lange ganze Zahl, `__int64` oder Struktur, abhängig von der Zielplattform\)|Wird von [fgetpos](../c-runtime-library/reference/fgetpos.md) und [fsetpos](../c-runtime-library/reference/fsetpos.md) verwendet, um Informationen für die eindeutige Angabe aller Positionen in einer Datei aufzuzeichnen.|STDIO.H|  
|`_fsize_t` \(lange ganze Zahl ohne Vorzeichen\)|Wird verwendet, um die Größe einer Datei anzuzeigen.|IO.H,<br /><br /> WCHAR.H|  
|`_HEAPINFO`\-Struktur|Enthält Informationen zum nächsten Heapeintrag für [\_heapwalk](../c-runtime-library/reference/heapwalk.md).|MALLOC.H|  
|`_HFILE` \(void \*\)|Ein Betriebssystem\-Dateihandle.|CRTDBG.H|  
|`imaxdiv_t`|Der Typ des Werts, der von der [imaxdiv](../c-runtime-library/reference/imaxdiv.md)\-Funktion zurückgegeben wird und den Quotienten und den Rest enthält.|inttypes.h|  
|`ino_t`, `_ino_t` \(kurz ohne Vorzeichen\)|Zur Rückgabe von Statusinformationen.|WCHAR.H|  
|`intmax_t`|Ein ganzzahliger Typ mit Vorzeichen, der beliebige Werte eines ganzzahligen Typs mit Vorzeichen darstellen kann.|stdint.h|  
|`intptr_t` \(lange ganze Zahl oder `__int64`, abhängig von der Zielplattform\)|Speichert einen Zeiger \(oder HANDLE\) auf Win32\- und Win64\-Plattformen.|STDDEF.H und andere Includedateien|  
|`jmp_buf`\-Array|Wird von [setjmp](../c-runtime-library/reference/setjmp.md) und [longjmp](../c-runtime-library/reference/longjmp.md) verwendet, um die Programmumgebung zu sichern und wiederherzustellen.|SETJMP.H|  
|`lconv`\-Struktur|Enthält Formatierungsregeln für numerische Werte in verschiedenen Ländern\/Regionen.  Wird durch [localeconv](../c-runtime-library/reference/localeconv.md) verwendet.|LOCALE.H|  
|`_LDOUBLE`,<br /><br /> `_LONGDOUBLE`,<br /><br /> `_LDBL12` \(long double\- oder vorzeichenloses Zeichenarray\)|Wird verwendet, um einen long double\-Wert darzustellen.|STDLIB.H|  
|`_locale_t`\-Struktur|Speichert aktuelle Gebietsschemawerte; wird in allen gebietsschemaspezifischen C\-Laufzeitbibliotheken verwendet.|CRTDEF.H|  
|`mbstate_t`|Verfolgt den Zustand einer Multibytezeichen\-Konvertierung.|WCHAR.H|  
|langer `off_t`, `_off_t`\-Integer|Stellt den Dateioffsetwert dar.|WCHAR.H, SYS\\TYPES.H|  
|`_onexit_t`,<br /><br /> `_onexit_m_t`\-Zeiger|Wird durch [\_onexit, \_onexit\_m](../c-runtime-library/reference/onexit-onexit-m.md) zurückgegeben.|STDLIB.H|  
|`_PNH`\-Zeiger auf eine Funktion|Typ des Arguments für [\_set\_new\_handler](../c-runtime-library/reference/set-new-handler.md).|NEW.H|  
|`ptrdiff_t` \(lange ganze Zahl oder `__int64`, abhängig von der Zielplattform\)|Ergebnis der Subtraktion von zwei Zeigern.|CRTDEFS.H|  
|`_purecall_handler`,<br /><br /> `_purecall_handler_m`|Eine Typendefinition für eine Rückruffunktion, die aufgerufen wird, wenn eine reine virtuelle Funktion aufgerufen wird.  Wird durch [\_get\_purecall\_handler \_set\_purecall\_handler](../c-runtime-library/reference/get-purecall-handler-set-purecall-handler.md) verwendet.  Eine `_purecall_handler`\-Funktion sollte einen ungültigen void\-Rückgabetyp haben.|STDLIB.H|  
|`_RTC_error_fn`\-Typendefinition|Eine Typendefinition für eine Funktion, die Laufzeitfehler\-Überprüfungen behandelt.  Wird in [\_RTC\_SetErrorFunc](../c-runtime-library/reference/rtc-seterrorfunc.md) verwendet.|RTCAPI.H|  
|`_RTC_error_fnW`\-Typendefinition|Eine Typendefinition für eine Funktion, die Laufzeitfehler\-Überprüfungen behandelt.  Wird in [\_RTC\_SetErrorFuncW](../c-runtime-library/reference/rtc-seterrorfuncw.md) verwendet.|RTCAPI.H|  
|`_RTC_ErrorNumber`\-Enumeration|Definiert Fehlerbedingungen für [\_RTC\_GetErrDesc](../c-runtime-library/reference/rtc-geterrdesc.md) und [\_RTC\_SetErrorType](../c-runtime-library/reference/rtc-seterrortype.md).|RTCAPI.H|  
|`_se_translator_function`|Eine Typendefinition für eine Rückruffunktion, die eine Ausnahme übersetzt.  Der erste Parameter ist der Ausnahmecode und der zweite Parameter ist der Ausnahmedatensatz.  Wird von [\_set\_se\_translator](../c-runtime-library/reference/set-se-translator.md) verwendet.|EH.H|  
|`sig_atomic_t`\-Integer|Objekttyp, der auch dann in eine atomare Entität geändert werden kann, wenn asynchrone Unterbrechungen vorhanden sind; wird mit [signal](../c-runtime-library/reference/signal.md) verwendet.|SIGNAL.H|  
|`size_t` \(\_\_int64 ohne Vorzeichen oder ganze Zahl ohne Vorzeichen, abhängig von der Zielplattform\)|Ergebnis des `sizeof`\-Operators.|CRTDEFS.H und andere Includedateien|  
|`_stat`\-Struktur|Enthält die Dateistatusinformationen, die von [\_stat](../c-runtime-library/reference/stat-functions.md) und [\_fstat](../c-runtime-library/reference/fstat-fstat32-fstat64-fstati64-fstat32i64-fstat64i32.md) zurückgegeben werden.|SYS\\STAT.H|  
|`__stat64`\-Struktur|Enthält die Dateistatusinformationen, die von [\_fstat64](../c-runtime-library/reference/fstat-fstat32-fstat64-fstati64-fstat32i64-fstat64i32.md) und [\_stat64](../c-runtime-library/reference/stat-functions.md) sowie [\_wstat64](../c-runtime-library/reference/stat-functions.md) zurückgegeben werden.|SYS\\STAT.H|  
|`_stati64`\-Struktur|Enthält die Dateistatusinformationen, die von [\_fstati64](../c-runtime-library/reference/fstat-fstat32-fstat64-fstati64-fstat32i64-fstat64i32.md), [\_stati64](../c-runtime-library/reference/stat-functions.md) und [\_wstati64](../c-runtime-library/reference/stat-functions.md) zurückgegeben werden.|SYS\\STAT.H|  
|`terminate_function`\-Typendefinition|Eine Typendefinition für eine Rückruffunktion, die aufgerufen wird, wenn [terminate](../c-runtime-library/reference/terminate-crt.md) aufgerufen wird.  Wird von [set\_terminate](../c-runtime-library/reference/set-terminate-crt.md) verwendet.|EH.H|  
|`time_t` \(\_\_int64 oder lange ganze Zahl\)|Repräsentiert Zeitwerte in [mktime](../c-runtime-library/reference/mktime-mktime32-mktime64.md), [time](../c-runtime-library/reference/time-time32-time64.md), [ctime, \_ctime32, \_ctime64, \_wctime, \_wctime32, \_wctime64](../c-runtime-library/reference/ctime-ctime32-ctime64-wctime-wctime32-wctime64.md), [ctime\_s, \_ctime32\_s, \_ctime64\_s, \_wctime\_s, \_wctime32\_s, \_wctime64\_s](../c-runtime-library/reference/ctime-s-ctime32-s-ctime64-s-wctime-s-wctime32-s-wctime64-s.md), [ctime, \_ctime32, \_ctime64, \_wctime, \_wctime32, \_wctime64](../c-runtime-library/reference/ctime-ctime32-ctime64-wctime-wctime32-wctime64.md) und [gmtime, \_gmtime32, \_gmtime64](../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md).  Die Anzahl der Sekunden seit dem 1. Januar 1970, 0:00 UTC.  Wenn \_USE\_32BIT\_TIME\_T definiert wird, ist `time_t` eine lange ganze Zahl.  Wenn es nicht definiert ist, ist es eine ganze 64\-Bit\-Zahl.|TIME.H,<br /><br /> SYS\\STAT.H,<br /><br /> SYS\\TIMEB.H|  
|`__time32_t` \(lange ganze Zahl\)|Repräsentiert Zeitwerte in [mktime, \_mktime32, \_mktime64](../c-runtime-library/reference/mktime-mktime32-mktime64.md), [ctime, \_ctime32, \_ctime64, \_wctime, \_wctime32, \_wctime64](../c-runtime-library/reference/ctime-ctime32-ctime64-wctime-wctime32-wctime64.md), [ctime\_s, \_ctime32\_s, \_ctime64\_s, \_wctime\_s, \_wctime32\_s, \_wctime64\_s](../c-runtime-library/reference/ctime-s-ctime32-s-ctime64-s-wctime-s-wctime32-s-wctime64-s.md), [gmtime, \_gmtime32, \_gmtime64](../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md) und [localtime, \_localtime32, \_localtime64](../c-runtime-library/reference/localtime-localtime32-localtime64.md).|CRTDEFS.H, SYS\\STAT.H,<br /><br /> SYS\\TIMEB.H|  
|`__time64_t` \(`__int64`\)|Repräsentiert Zeitwerte in [mktime, \_mktime32, \_mktime64](../c-runtime-library/reference/mktime-mktime32-mktime64.md), [\_ctime64, \_wctime64](../c-runtime-library/reference/ctime-ctime32-ctime64-wctime-wctime32-wctime64.md), [ctime\_s, \_ctime32\_s, \_ctime64\_s, \_wctime\_s, \_wctime32\_s, \_wctime64\_s](../c-runtime-library/reference/ctime-s-ctime32-s-ctime64-s-wctime-s-wctime32-s-wctime64-s.md), [\_gmtime64](../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md), [\_localtime64](../c-runtime-library/reference/localtime-localtime32-localtime64.md) und [\_time64](../c-runtime-library/reference/time-time32-time64.md).|TIME.H,<br /><br /> SYS\\STAT.H,<br /><br /> SYS\\TIMEB.H|  
|`_timeb`\-Struktur|Wird durch [\_ftime](../c-runtime-library/reference/ftime-ftime32-ftime64.md) und [\_ftime\_s, \_ftime32\_s, \_ftime64\_s](../c-runtime-library/reference/ftime-s-ftime32-s-ftime64-s.md) verwendet, um die aktuelle Systemzeit zu speichern.|SYS\\TIMEB.H|  
|`__timeb32`\-Struktur|Wird durch [\_ftime, \_ftime32, \_ftime64](../c-runtime-library/reference/ftime-ftime32-ftime64.md) und [\_ftime\_s, \_ftime32\_s, \_ftime64\_s](../c-runtime-library/reference/ftime-s-ftime32-s-ftime64-s.md) verwendet, um die aktuelle Systemzeit zu speichern.|SYS\\TIMEB.H|  
|`__timeb64`\-Struktur|Wird durch [\_ftime64](../c-runtime-library/reference/ftime-ftime32-ftime64.md)und [\_ftime\_s, \_ftime32\_s, \_ftime64\_s](../c-runtime-library/reference/ftime-s-ftime32-s-ftime64-s.md) verwendet, um die aktuelle Systemzeit zu speichern.|SYS\\TIMEB.H|  
|`tm`\-Struktur|Wird durch [asctime, \_wasctime](../c-runtime-library/reference/asctime-wasctime.md), [asctime\_s, \_wasctime\_s](../c-runtime-library/reference/asctime-s-wasctime-s.md), [gmtime, \_gmtime32, \_gmtime64](../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md), [gmtime\_s, \_gmtime32\_s, \_gmtime64\_s](../c-runtime-library/reference/gmtime-s-gmtime32-s-gmtime64-s.md), [localtime, \_localtime32, \_localtime64](../c-runtime-library/reference/localtime-localtime32-localtime64.md), [localtime\_s, \_localtime32\_s, \_localtime64\_s](../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md), [mktime, \_mktime32, \_mktime64](../c-runtime-library/reference/mktime-mktime32-mktime64.md) und [strftime, wcsftime, \_strftime\_l, \_wcsftime\_l](../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md) verwendet, um Uhrzeitinformationen zu speichern und abzurufen.|TIME.H|  
|`uintmax_t`|Ein ganzzahliger Typ ohne Vorzeichen, der einen beliebigen Wert eines ganzzahligen Typs ohne Vorzeichen darstellen kann.|stdint.h|  
|`uintptr_t` \(lange ganze Zahl oder `__int64`, abhängig von der Zielplattform\)|Eine ganze Zahl ohne Vorzeichen oder eine \_\_int64\-Version ohne Vorzeichen von `intptr_t`.|STDDEF.H und andere Includedateien|  
|`unexpected_function`|Eine Typendefinition für eine Rückruffunktion, die aufgerufen wird, wenn [unexpected](../c-runtime-library/reference/unexpected-crt.md) aufgerufen wird.  Wird von [set\_unexpected](../c-runtime-library/reference/set-unexpected-crt.md) verwendet.|EH.H|  
|`_utimbuf`\-Struktur|Speichert Dateizugriffs\- und Änderungszeiten, die von [\_utime, \_wutime](../c-runtime-library/reference/utime-utime32-utime64-wutime-wutime32-wutime64.md) und [\_futime, \_futime32, \_futime64](../c-runtime-library/reference/futime-futime32-futime64.md) verwendet werden, um Datumsangaben zu Dateiänderungen zu ändern.|SYS\\UTIME.H|  
|`_utimbuf32`\-Struktur|Speichert Dateizugriffs\- und Änderungszeiten, die von [\_utime, \_utime32, \_utime64, \_wutime, \_wutime32, \_wutime64](../c-runtime-library/reference/utime-utime32-utime64-wutime-wutime32-wutime64.md) und [\_futime, \_futime32, \_futime64](../c-runtime-library/reference/futime-futime32-futime64.md) verwendet werden, um Datumsangaben zu Dateiänderungen zu ändern.|SYS\\UTIME.H|  
|`__utimbuf64`\-Struktur|Wird von [\_utime64, \_wutime64](../c-runtime-library/reference/utime-utime32-utime64-wutime-wutime32-wutime64.md) und [\_futime64](../c-runtime-library/reference/futime-futime32-futime64.md) zum Speichern der aktuellen Zeit verwendet.|SYS\\UTIME.H|  
|`va_list`\-Struktur|Wird zum Speichern von Informationen verwendet, die von [va\_arg](../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md)\- und [va\_end](../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md)\-Makros benötigt werden.  Die aufgerufene Funktion deklariert Variablen vom Typ `va_list`, die als Argument einer anderen Funktion übergeben werden können.|STDARG.H,<br /><br /> CRTDEFS.H|  
|`wchar_t`\-Breitzeichen|Eignet sich zum Schreiben übertragbarer Programmen für internationale Märkte.|STDDEF.H, STDLIB.H,<br /><br /> CRTDEFS.H,<br /><br /> SYS\\STAT.H|  
|`wctrans_t`\-Integer|Stellt gebietsschemaspezifische Zeichenzuordnungen dar.|WCTYPE.H|  
|`wctype_t`\-Integer|Es können alle Zeichen eines beliebigen Sprachenzeichensatzes dargestellt werden.|WCHAR.H,<br /><br /> CRTDEFS.H|  
|`wint_t`\-Integer|Typ eines Datenobjekts, der beliebige Breitzeichen\- oder Breitzeichen\-Dateiende\-Werte enthalten kann.|WCHAR.H,<br /><br /> CRTDEFS.H|  
  
## Siehe auch  
 [C\-Laufzeitbibliotheksverweis](../c-runtime-library/c-run-time-library-reference.md)