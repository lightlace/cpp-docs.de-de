---
title: "_configthreadlocale"
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
  - "_configthreadlocale"
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
  - "api-ms-win-crt-locale-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_configthreadlocale"
  - "configthreadlocale"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_configthreadlocale-Funktion"
  - "configthreadlocale-Funktion"
  - "Gebietsschemas, pro Thread"
  - "Threadspezifisches Gebietsschema"
  - "Threadgebietsschema"
ms.assetid: 10e4050e-b587-4f30-80bc-6c76b35fc770
caps.latest.revision: 24
caps.handback.revision: "22"
ms.author: "corob"
manager: "ghogen"
---
# _configthreadlocale
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Konfiguriert Optionen für threadspezifische Gebietsschemas.  
  
## Syntax  
  
```  
int _configthreadlocale(  
   int type  
);  
```  
  
#### Parameter  
 `type`  
 Die festzulegende Option.  Eine der in der folgenden Tabelle aufgelisteten Optionen.  
  
## Rückgabewert  
 Der vorherige Status des threadspezifischen Gebietsschemas \(`_DISABLE_PER_THREAD_LOCALE` oder `_ENABLE_PER_THREAD_LOCALE`\) oder "– 1", wenn ein Fehler auftritt.  
  
## Hinweise  
 Mit der `_configurethreadlocale`\-Funktion wird die Verwendung von threadspezifischen Gebietsschemas gesteuert.  Verwenden Sie eine dieser Optionen, um den Status des threadspezifischen Gebietsschemas anzugeben oder zu bestimmen:  
  
 `_ENABLE_PER_THREAD_LOCALE`  
 Legen Sie fest, dass der aktuelle Thread ein threadspezifisches Gebietsschema verwendet.  Nachfolgende Aufrufe von `setlocale` in diesem Thread betreffen nur das eigene Gebietsschema des Threads.  
  
 `_DISABLE_PER_THREAD_LOCALE`  
 Legen Sie fest, dass der aktuelle Thread das globale Gebietsschema verwendet.  Nachfolgende Aufrufe von `setlocale` in diesem Thread wirken sich auch auf andere Threads aus, die das globale Gebietsschema verwenden.  
  
 `0`  
 Ruft die aktuelle Einstellung für diesen speziellen Thread ab.  
  
 Diese Funktionen beeinflussen das Verhalten von `setlocale`, `_tsetlocale`, `_wsetlocale`, `_beginthread` und  `_beginthreadex`.  Wenn eine andere Methode zum Erstellen von Threads verwendet wird, haben die Gebietsschemaeinstellungen keine Auswirkungen auf diese Threads.  
  
 Wenn das threadspezifische Gebietsschema deaktiviert ist, ändert jeder nachfolgende Aufruf von `setlocale` oder `_wsetlocale` das Gebietsschema aller Threads.  Wenn das threadspezifische Gebietsschema aktiviert ist, wirken sich `setlocale` oder `_wsetlocale` nur auf das Gebietsschema des aktuellen Threads aus.  
  
 Bei Verwendung von `_configurethreadlocale` zur Aktivierung eines threadspezifischen Gebietsschemas wird empfohlen, `setlocale` oder `_wsetlocale` aufrufen, um unmittelbar danach das bevorzugte Gebietsschema in diesem Thread festzulegen.  
  
 Wenn `type` keinen der in der Tabelle aufgeführten Werte aufweist, ruft diese Funktion den Handler für ungültige Parameter auf, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben.  Wenn die weitere Ausführung zugelassen wird, legt diese Funktion `errno` auf `EINVAL` fest und gibt "– 1" zurück.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_configthreadlocale`|\<locale.h\>|  
  
## Beispiel  
  
```  
// crt_configthreadlocale.cpp  
//   
// This program demonstrates the use of _configthreadlocale when  
// using is two independent threads.  
//  
  
#include <locale.h>  
#include <process.h>  
#include <windows.h>  
#include <stdio.h>  
#include <time.h>  
  
#define BUFF_SIZE 100  
  
// Retrieve the date and time in the current  
// locale's format.  
int get_time(unsigned char* str)  
{  
    __time64_t  ltime;  
    struct tm   thetime;  
  
    // Retieve the time  
    _time64(&ltime);  
    _gmtime64_s(&thetime, &ltime);  
  
    // Format the current time structure into a string  
    // using %#x is the long date representation,  
    // appropriate to the current locale  
    if (!strftime((char *)str, BUFF_SIZE, "%#x",   
                  (const struct tm*)&thetime))  
    {  
        printf("strftime failed!\n");  
        return -1;  
    }  
    return 0;  
}  
  
// This thread sets its locale to German  
// and prints the time.  
unsigned __stdcall SecondThreadFunc( void* pArguments )  
{  
    unsigned char str[BUFF_SIZE];  
  
    // Set the thread code page  
    _setmbcp(_MB_CP_ANSI)  
  
    // Set the thread locale  
    printf("The thread locale is now set to %s.\n",  
           setlocale(LC_ALL, "German"));  
  
    // Retrieve the time string from the helper function  
    if (get_time(str) == 0)  
    {  
        printf("The time in German locale is: '%s'\n", str);  
    }  
  
    _endthreadex( 0 );  
    return 0;  
}   
  
// The main thread spawns a second thread (above) and then  
// sets the locale to English and prints the time.  
int main()  
{   
    HANDLE          hThread;  
    unsigned        threadID;  
    unsigned char   str[BUFF_SIZE];  
  
    // Configure per-thread locale to cause all subsequently created   
    // threads to have their own locale.  
    _configthreadlocale(_ENABLE_PER_THREAD_LOCALE);  
  
    // Retrieve the time string from the helper function  
    printf("The thread locale is now set to %s.\n",  
           setlocale(LC_ALL, "English"));  
  
    // Create the second thread.  
    hThread = (HANDLE)_beginthreadex( NULL, 0, &SecondThreadFunc,  
                                      NULL, 0, &threadID );  
  
    if (get_time(str) == 0)  
    {  
        // Retrieve the time string from the helper function  
        printf("The time in English locale is: '%s'\n\n", str);  
    }  
  
    // Wait for the created thread to finish.  
    WaitForSingleObject( hThread, INFINITE );  
  
    // Destroy the thread object.  
    CloseHandle( hThread );  
}  
```  
  
  **Das Threadgebietsschema wird jetzt auf English\_United States.1252 festgelegt.**  
**Die Zeit im englischen Gebietsschema ist: "Mittwoch, 12. Mai 2004"**  
**Das Threadgebietsschema wird jetzt auf German\_Germany.1252 festgelegt.**  
**Die Zeit im deutschen Gebietsschema ist: "Mittwoch, 12.  Mai 2004"**    
## .NET Framework-Entsprechung  
 Nicht zutreffend. Weitere Informationen finden Sie jedoch auch unter [Verwenden der CurrentCulture\-Eigenschaft](assetId:///3156042d-6082-4205-90b4-c917ae6a3ba6).  
  
## Siehe auch  
 [setlocale, \_wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)   
 [\_beginthread, \_beginthreadex](../../c-runtime-library/reference/beginthread-beginthreadex.md)   
 [Locale](../../c-runtime-library/locale.md)   
 [Multithreading und Gebietsschemas](../../parallel/multithreading-and-locales.md)