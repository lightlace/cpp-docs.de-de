---
title: "asctime_s, _wasctime_s"
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
  - "_wasctime_s"
  - "asctime_s"
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
  - "asctime_s"
  - "_wasctime_s"
  - "_tasctime_s"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_tasctime_s-Funktion"
  - "_wasctime_s-Funktion"
  - "asctime_s-Funktion"
  - "tasctime_s-Funktion"
  - "Zeitstrukturkonvertierung"
  - "Uhrzeit, Konvertieren"
  - "wasctime_s-Funktion"
ms.assetid: 17ad9b2b-a459-465d-976a-42822897688a
caps.latest.revision: 29
caps.handback.revision: "27"
ms.author: "corob"
manager: "ghogen"
---
# asctime_s, _wasctime_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Konvertiert eine Zeitstruktur `tm` in eine Zeichenfolge.  Diese Funktionen sind Versionen von [asctime, \_wasctime](../../c-runtime-library/reference/asctime-wasctime.md) mit werden, wie in [Sicherheitsfunktionen in der CRT](../../c-runtime-library/security-features-in-the-crt.md) beschrieben.  
  
## Syntax  
  
```  
errno_t asctime_s(   
   char* buffer,  
   size_t numberOfElements,  
   const struct tm *_tm   
);  
errno_t _wasctime_s(   
   wchar_t* buffer,  
   size_t numberOfElements  
   const struct tm *_tm   
);  
template <size_t size>  
errno_t asctime_s(   
   char (&buffer)[size],  
   const struct tm *_tm   
); // C++ only  
template <size_t size>  
errno_t _wasctime_s(   
   wchar_t (&buffer)[size],  
   const struct tm *_tm   
); // C++ only  
```  
  
#### Parameter  
 `buffer`  
 \[out\] Ein Zeiger auf einen Puffer, um den Zeichenfolgenergebnisses zu speichern.  Diese Funktion verwendet einen Zeiger auf eine gültige Speicheradresse mit einer Größe an, die von `numberOfElements` angegeben wird.  
  
 `numberOfElements`  
 \[in\] Die Größe des Puffers verwendet, um das Ergebnis zu speichern.  
  
 `_tm`  
 \[in\] Datum\-\/Uhrzeit\-Struktur.  Diese Funktion verwendet einen Zeiger auf ein gültiges Objekt `struct``tm` an.  
  
## Rückgabewert  
 Null wenn erfolgreich.  Wenn es einen Fehler enthält, wird der ungültige Parameterhandler aufgerufen, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben.  Wenn die Ausführung zulässig ist, um fortzufahren, ist der Rückgabewert ein Fehlercode.  Fehlercodes werden in ERRNO.H. definiert.  Weitere Informationen finden Sie unter [errno\-Konstanten](../../c-runtime-library/errno-constants.md).  Die tatsächlichen Fehlercodes, die für jeden Fehlerzustand zurückgegeben werden, werden in der folgenden Tabelle dargestellt.  
  
### Fehlerbedingungen  
  
|`buffer`|`numberOfElements`|`tm`|Return|Wert in `buffer`|  
|--------------|------------------------|----------|------------|----------------------|  
|`NULL`|Irgendein|Irgendein|`EINVAL`|Nicht geändert|  
|Nicht `NULL` \(Punkte zum gültigen Arbeitsspeicher\)|0|Irgendein|`EINVAL`|Nicht geändert|  
|Nicht `NULL`|0\< Größe \< 26|Irgendein|`EINVAL`|Leere Zeichenfolge|  
|Nicht `NULL`|\>\= 26|`NULL`|`EINVAL`|Leere Zeichenfolge|  
|Nicht `NULL`|\>\= 26|Ungültige Zeitstruktur oder aus Bereichswerten für Komponenten der die Zeit abgelaufen|`EINVAL`|Leere Zeichenfolge|  
  
> [!NOTE]
>  Fehlerzustände für `wasctime_s` sind mit `asctime_s` vergleichbar, mit der Ausnahme, dass wird die Größenbeschränkung in Worten gemessen.  
  
## Hinweise  
 Die `asctime`\-Funktion konvertiert eine Zeit, die als Struktur einer Zeichenfolge gespeichert ist.  Der Wert `_tm` wird normalerweise von einem Aufruf von `gmtime` oder `localtime` erhalten.  Beide Funktionen können verwendet werden, um eine Struktur `tm` auszufüllen, wie in TIME.H. definiert.  
  
|timeptr Member|Wert|  
|--------------------|----------|  
|`tm_hour`|Stunden ab Mitternacht \(0\-23\)|  
|`tm_isdst`|Positiv, wenn Sommerzeit wirksam ist; 0 die Sommerzeit nicht aktiv ist; Negativ, wenn Status der Sommerzeit nicht bekannt ist.  Die C\-Laufzeitbibliothek die akzeptiert der Vereinigten Staaten Regeln zum Implementieren der Berechnung der Sommerzeit \(DST\) an.|  
|`tm_mday`|Tag des Monats \(1\-31\)|  
|`tm_min`|Minuten nach Stunde \(0\-59\)|  
|`tm_mon`|Monat \(0\-11; Januar \= 0\)|  
|`tm_sec`|Sekunden nach Minute \(0\-59\)|  
|`tm_wday`|Wochentag \(0\-6; Sonntag \= 0\)|  
|`tm_yday`|Tag des Jahres \(0\-365; Am 1. Januar \= 0\)|  
|`tm_year`|Jahr \(Open\-Wheel\-Racing\-Team Jahr minus 1900\)|  
  
 Die konvertierte Zeichenfolge wird auch nach den Einstellungen der lokalen Zeitzone angepasst.  Siehe [time, \_time32, \_time64](../../c-runtime-library/reference/time-time32-time64.md), [\_ftime, \_ftime32, \_ftime64](../../c-runtime-library/reference/ftime-ftime32-ftime64.md) und [localtime\_s, \_localtime32\_s, \_localtime64\_s](../../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md)\-Funktionen zu Informationen zum Konfigurieren der Ortszeit und der [\_tzset](../../c-runtime-library/reference/tzset.md)\-Funktion zu Informationen über das Definieren der Zeitzonenumgebung und der globalen Variablen.  
  
 Das Zeichenfolgenergebnis, das von `asctime_s` erzeugt wird, enthält genau 26 Zeichen und weist das Format `Wed Jan 02 02:03:55 1980\n\0`.  Ein 24\-Stunden\-Format wird verwendet.  Alle Felder verfügen eine konstante Breite.  Das Zeilenumbruchzeichen und das Nullzeichen nehmen die letzten zwei Positionen der Zeichenfolge ein.  Der Wert, der in als zweiten Parameter übergeben wird, sollte dieser großer mindestens sein.  Wenn er kleiner ist, wird ein Fehlercode, `EINVAL`, zurückgegeben.  
  
 `_wasctime_s` ist eine Breitzeichenversion von `asctime_s`.  `_wasctime_s` und `asctime_s` verhalten sich andernfalls identisch.  
  
### Zuordnung generische Textroutinen  
  
|TCHAR.H\-Routine|\_UNICODE & \_MBCS nicht definiert|\_MBCS definiert|\_UNICODE definiert|  
|----------------------|----------------------------------------|----------------------|-------------------------|  
|`_tasctime_s`|`asctime_s`|`asctime_s`|`_wasctime_s`|  
  
 Die Verwendung dieser Funktionen in C\+\+ wird durch Überladungen \(als Vorlagen vorhanden\) vereinfacht. Überladungen können automatisch die Pufferlänge ableiten, sodass kein Größenargument angegeben werden muss.  Weitere Informationen finden Sie unter [Sichere Vorlagenüberladungen](../../c-runtime-library/secure-template-overloads.md).  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`asctime_s`|\<time.h\>|  
|`_wasctime_s`|\<time.h oder\> wchar.h \<\>|  
  
## Sicherheit  
 Wenn der Pufferzeiger nicht `NULL` und der Zeiger nicht auf einen gültigen Puffer wird, überschreibt die Funktion, was am Speicherort befindet.  Dies kann eine Zugriffsverletzung auch führen.  
  
 [Pufferüberlauf](http://msdn.microsoft.com/library/windows/desktop/ms717795) kann auftreten, wenn das Größenargument, das übergeben wird, größer das tatsächliche Größe des Puffers ist.  
  
## Beispiel  
 Dieses Programm platziert die Systemzeit in langen ganzzahligen `aclock`, übersetzt sie in die `newtime`\-Struktur und konvertiert sie anschließend in Zeichenfolgenform für Ausgaben, mit der `asctime_s`\-Funktion.  
  
```  
// crt_asctime_s.c  
#include <time.h>  
#include <stdio.h>  
  
struct tm newtime;  
__time32_t aclock;  
  
int main( void )  
{  
   char buffer[32];  
   errno_t errNum;  
   _time32( &aclock );   // Get time in seconds.  
   _localtime32_s( &newtime, &aclock );   // Convert time to struct tm form.  
  
   // Print local time as a string.  
  
   errNum = asctime_s(buffer, 32, &newtime);  
   if (errNum)  
   {  
       printf("Error code: %d", (int)errNum);  
       return 1;  
   }  
   printf( "Current date and time: %s", buffer );  
   return 0;  
}  
```  
  
  **Aktuelles Datum und Uhrzeit: Am Mittwoch, den 14. Mai 15: 30:17 2003**   
## .NET Framework-Entsprechung  
  
-   <xref:System.DateTime.ToLongDateString*?displayProperty=fullName>  
  
-   <xref:System.DateTime.ToLongTimeString*?displayProperty=fullName>  
  
-   <xref:System.DateTime.ToShortDateString*?displayProperty=fullName>  
  
-   <xref:System.DateTime.ToShortTimeString*?displayProperty=fullName>  
  
-   <xref:System.DateTime.ToString*?displayProperty=fullName>  
  
## Siehe auch  
 [Uhrzeitverwaltung](../../c-runtime-library/time-management.md)   
 [ctime\_s, \_ctime32\_s, \_ctime64\_s, \_wctime\_s, \_wctime32\_s, \_wctime64\_s](../../c-runtime-library/reference/ctime-s-ctime32-s-ctime64-s-wctime-s-wctime32-s-wctime64-s.md)   
 [\_ftime, \_ftime32, \_ftime64](../../c-runtime-library/reference/ftime-ftime32-ftime64.md)   
 [gmtime\_s, \_gmtime32\_s, \_gmtime64\_s](../../c-runtime-library/reference/gmtime-s-gmtime32-s-gmtime64-s.md)   
 [localtime\_s, \_localtime32\_s, \_localtime64\_s](../../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md)   
 [time, \_time32, \_time64](../../c-runtime-library/reference/time-time32-time64.md)   
 [\_tzset](../../c-runtime-library/reference/tzset.md)