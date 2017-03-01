---
title: _configthreadlocale | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _configthreadlocale
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
- api-ms-win-crt-locale-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _configthreadlocale
- configthreadlocale
dev_langs:
- C++
helpviewer_keywords:
- configthreadlocale function
- locales, per-thread
- _configthreadlocale function
- per-thread locale
- thread locale
ms.assetid: 10e4050e-b587-4f30-80bc-6c76b35fc770
caps.latest.revision: 24
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 1fca01932efb2f80d4aebf94db8900cee5d79805
ms.lasthandoff: 02/24/2017

---
# <a name="configthreadlocale"></a>_configthreadlocale
Konfiguriert Optionen für threadspezifische Gebietsschemas.  
  
## <a name="syntax"></a>Syntax  
  
```  
int _configthreadlocale(  
   int type  
);  
```  
  
### <a name="parameters"></a>Parameter  
 `type`  
 Die festzulegende Option. Eine der in der folgenden Tabelle aufgelisteten Optionen.  
  
## <a name="return-value"></a>Rückgabewert  
 Der vorherige Status des threadspezifischen Gebietsschemas (`_DISABLE_PER_THREAD_LOCALE` oder `_ENABLE_PER_THREAD_LOCALE`) oder "–&1;", wenn ein Fehler auftritt.  
  
## <a name="remarks"></a>Hinweise  
 Mit der `_configurethreadlocale`-Funktion wird die Verwendung von threadspezifischen Gebietsschemas gesteuert. Verwenden Sie eine dieser Optionen, um den Status des threadspezifischen Gebietsschemas anzugeben oder zu bestimmen:  
  
 `_ENABLE_PER_THREAD_LOCALE`  
 Legen Sie fest, dass der aktuelle Thread ein threadspezifisches Gebietsschema verwendet. Nachfolgende Aufrufe von `setlocale` in diesem Thread betreffen nur das eigene Gebietsschema des Threads.  
  
 `_DISABLE_PER_THREAD_LOCALE`  
 Legen Sie fest, dass der aktuelle Thread das globale Gebietsschema verwendet. Nachfolgende Aufrufe von `setlocale` in diesem Thread wirken sich auch auf andere Threads aus, die das globale Gebietsschema verwenden.  
  
 `0`  
 Ruft die aktuelle Einstellung für diesen speziellen Thread ab.  
  
 Diese Funktionen beeinflussen das Verhalten der `setlocale`, `_tsetlocale`, und `_wsetlocale`. Wenn threadspezifische Gebietsschema deaktiviert ist, alle nachfolgenden Aufruf ist `setlocale` oder `_wsetlocale` ändert das Gebietsschema aller Threads, die das globale Gebietsschema verwendet. Wenn das threadspezifische Gebietsschema aktiviert ist, wirken sich `setlocale` oder `_wsetlocale` nur auf das Gebietsschema des aktuellen Threads aus.  
  
 Bei Verwendung von `_configurethreadlocale` zur Aktivierung eines threadspezifischen Gebietsschemas wird empfohlen, `setlocale` oder `_wsetlocale` aufrufen, um unmittelbar danach das bevorzugte Gebietsschema in diesem Thread festzulegen.  
  
 Wenn `type` keiner der in der Tabelle aufgeführten Werte ist, ruft diese Funktion den Handler für ungültige Parameter auf, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben. Wenn die weitere Ausführung zugelassen wird, setzt diese Funktion `errno` auf `EINVAL` und gibt "-1" zurück.  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------|  
|`_configthreadlocale`|\<locale.h>|  
  
## <a name="example"></a>Beispiel  
  
```cpp  
// crt_configthreadlocale.cpp  
//   
// This program demonstrates the use of _configthreadlocale when  
// using two independent threads.  
//  
// Compile by using: cl /EHsc /W4 crt_configthreadlocale.cpp 
  
#include <locale.h>  
#include <mbctype.h>  
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
unsigned __stdcall SecondThreadFunc( void* /*pArguments*/ )  
{  
    unsigned char str[BUFF_SIZE];  
  
    _configthreadlocale(_ENABLE_PER_THREAD_LOCALE);  

    // Set the thread code page  
    _setmbcp(_MB_CP_ANSI);  
  
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
  
    // Enable per-thread locale causes all subsequent locale   
    // setting changes in this thread to only affect this thread.  
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
  
```Output  
The thread locale is now set to English_United States.1252.  
The time in English locale is: 'Wednesday, May 12, 2004'  
  
The thread locale is now set to German_Germany.1252.  
The time in German locale is: 'Mittwoch, 12. Mai 2004'  
```  
  
## <a name="see-also"></a>Siehe auch  
 [setlocale, _wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)   
 [_beginthread, _beginthreadex](../../c-runtime-library/reference/beginthread-beginthreadex.md)   
 [Gebietsschema](../../c-runtime-library/locale.md)   
 [Multithreading und Gebietsschemas](../../parallel/multithreading-and-locales.md)  

