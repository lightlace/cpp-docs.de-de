---
title: _configthreadlocale | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
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
ms.workload:
- cplusplus
ms.openlocfilehash: f8bed665719639a70a2a163356e13df57f6c8578
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2018
---
# <a name="configthreadlocale"></a>_configthreadlocale

Konfiguriert Optionen für threadspezifische Gebietsschemas.

## <a name="syntax"></a>Syntax

```C
int _configthreadlocale( int per_thread_locale_type );
```

### <a name="parameters"></a>Parameter

*per_thread_locale_type*<br/>
Die festzulegende Option. Eine der in der folgenden Tabelle aufgelisteten Optionen.

## <a name="return-value"></a>Rückgabewert

Der vorherige Status des threadspezifischen Gebietsschemas (**_DISABLE_PER_THREAD_LOCALE** oder **_ENABLE_PER_THREAD_LOCALE**), oder -1, bei einem Fehler.

## <a name="remarks"></a>Hinweise

Die **_configurethreadlocale** Funktion wird verwendet, um die Verwendung von threadspezifischen Gebietsschemas gesteuert. Verwenden Sie eines der folgenden *Per_thread_locale_type* Optionen angeben oder den Status des threadspezifischen Gebietsschemas ermitteln:

|||
|-|-|
**_ENABLE_PER_THREAD_LOCALE**|Legen Sie fest, dass der aktuelle Thread ein threadspezifisches Gebietsschema verwendet. Nachfolgende Aufrufe **Setlocale** in diesem Thread betreffen nur das eigene Gebietsschema des Threads.
**_DISABLE_PER_THREAD_LOCALE**|Legen Sie fest, dass der aktuelle Thread das globale Gebietsschema verwendet. Nachfolgende Aufrufe **Setlocale** in diesem Thread wirken sich auf andere Threads, die das globale Gebietsschema verwenden.
**0**|Ruft die aktuelle Einstellung für diesen speziellen Thread ab.

Diese Funktionen beeinflussen das Verhalten des **Setlocale**, **_tsetlocale**, **_wsetlocale**, und **_setmbcp**. Wenn threadspezifisches Gebietsschema ist deaktiviert, die jeder nachfolgende Aufruf von **Setlocale** oder **_wsetlocale** ändert das Gebietsschema aller Threads, die das globale Gebietsschema verwenden. Wenn das threadspezifische Gebietsschema aktiviert ist, **Setlocale** oder **_wsetlocale** wirkt sich nur auf das Gebietsschema des aktuellen Threads.

Bei Verwendung von **_configurethreadlocale** zum Aktivieren eines threadspezifischen Gebietsschemas wird empfohlen, die Sie aufrufen **Setlocale** oder **_wsetlocale** auf das bevorzugte Gebietsschema in diesem Thread festzulegen. unmittelbar danach.

Wenn *Per_thread_locale_type* ist keiner der Werte in der Tabelle aufgeführten, ruft diese Funktion den Handler für ungültige Parameter wie beschrieben in [Parametervalidierung](../../c-runtime-library/parameter-validation.md). Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, setzt diese Funktion **Errno** auf **EINVAL** und gibt-1 zurück.

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|
|-------------|---------------------|
|**_configthreadlocale**|\<locale.h>|

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

[setlocale, _wsetlocale](setlocale-wsetlocale.md)<br/>
[_beginthread, _beginthreadex](beginthread-beginthreadex.md)<br/>
[Locale](../../c-runtime-library/locale.md)<br/>
[Multithreading und Gebietsschemas](../../parallel/multithreading-and-locales.md)<br/>
