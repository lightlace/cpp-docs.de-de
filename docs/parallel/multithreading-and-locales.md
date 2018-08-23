---
title: Multithreading und Gebietsschemas | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- locales [C++], multithreading
- multithreading [C++], locales
- threading [C++], locales
- per-thread locale
ms.assetid: d6fb159a-eaca-4130-a51a-f95d62f71485
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0506c7f4efd288417c8fbdcd4784446651c362ac
ms.sourcegitcommit: e9ce38decc9f986edab5543de3464b11ebccb123
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/13/2018
ms.locfileid: "42540004"
---
# <a name="multithreading-and-locales"></a>Multithreading und Gebietsschemas
Sowohl C-Laufzeitbibliothek und C++-Standardbibliothek bieten Unterstützung für die Änderung des Gebietsschemas für Ihr Programm ein. Dieses Thema behandelt Probleme, die auftreten, wenn Sie die Gebietsschema-Funktionen der beiden Bibliotheken in einer Multithreadanwendung zu verwenden.  
  
## <a name="remarks"></a>Hinweise  

Mit der C-Laufzeitbibliothek können Sie mithilfe von Multithreadanwendungen erstellen die `_beginthread` und `_beginthreadex` Funktionen. Dieses Thema behandelt nur Multithread-Anwendungen unter Verwendung dieser Funktionen erstellt. Weitere Informationen finden Sie unter [_beginthread, _beginthreadex](../c-runtime-library/reference/beginthread-beginthreadex.md).  
  
Verwenden Sie zum Ändern des Gebietsschemas mithilfe von C-Laufzeitbibliothek die [Setlocale](../preprocessor/setlocale.md) Funktion. In früheren Versionen von Visual C++ würde diese Funktion immer das Gebietsschema in der gesamten Anwendung ändern. Es gibt jetzt Unterstützung für das Festlegen des Gebietsschemas auf einer pro-Thread-Basis. Dies erfolgt mithilfe der [_configthreadlocale](../c-runtime-library/reference/configthreadlocale.md) Funktion. Um anzugeben, dass [Setlocale](../preprocessor/setlocale.md) sollten nur ändern, das den aktuellen Thread Aufruf verwendete Gebietsschema `_configthreadlocale(_ENABLE_PER_THREAD_LOCALE)` in diesem Thread. Umgekehrt wird beim Aufruf `_configthreadlocale(_DISABLE_PER_THREAD_LOCALE)` führt dazu, dass dieser Thread auf das globale Gebietsschema verwendet, und jeder Aufruf von [Setlocale](../preprocessor/setlocale.md) darin, dass Thread das Gebietsschema aller Threads ändert, die nicht explizit threadspezifische Gebietsschema aktiviert haben.  
  
Verwenden Sie zum Ändern des Gebietsschemas mithilfe C++-Laufzeitbibliothek die [Locale-Klasse](../standard-library/locale-class.md). Durch Aufrufen der [locale:: Global](../standard-library/locale-class.md#global) -Methode, ändern Sie das Gebietsschema in allen Threads, die nicht explizit threadspezifische Gebietsschema aktiviert ist. Um das Gebietsschema in einem einzigen Thread oder einen Teil einer Anwendung zu ändern, erstellen Sie eine Instanz einer `locale` Objekt in diesem Thread oder einen Teil des Codes.  
  
> [!NOTE]
> Aufrufen von [locale:: Global](../standard-library/locale-class.md#global) ändert das Gebietsschema für C-Laufzeitbibliothek und C++-Standardbibliothek. Das Aufrufen von jedoch [Setlocale](../preprocessor/setlocale.md) ändert nur das Gebietsschema für C-Laufzeitbibliothek, die C++-Standardbibliothek ist nicht betroffen.  
  
Die folgenden Beispiele zeigen, wie Sie mit der [Setlocale](../preprocessor/setlocale.md) -Funktion, die [Locale-Klasse](../standard-library/locale-class.md), und die [_configthreadlocale](../c-runtime-library/reference/configthreadlocale.md) Funktion, um eine Anwendung in das Gebietsschema ändern mehrere verschiedene Szenarien.  
  
## <a name="example"></a>Beispiel  
 
In diesem Beispiel erzeugt der Hauptthread zwei untergeordnete Threads. Der erste Thread, Thread A aktiviert threadspezifisches Gebietsschema durch Aufrufen von `_configthreadlocale(_ENABLE_PER_THREAD_LOCALE)`. Der zweite Thread, Thread B als auch den Hauptthread, aktivieren Sie threadspezifisches Gebietsschema nicht. Thread A wird anschließend fortgesetzt wird, so ändern Sie das Gebietsschema mit dem [Setlocale](../preprocessor/setlocale.md) Funktion der C-Laufzeitbibliothek.  
  
Da der Thread ein threadspezifisches Gebietsschema aktiviert ist, nur die C-Laufzeitbibliothek-Funktionen im Thread A Einstieg in das Gebietsschema "Französisch" hat. Die C-Laufzeitbibliothek-Funktionen in Thread B und im Hauptthread weiterhin das Gebietsschema "C" verwenden. Da außerdem [Setlocale](../preprocessor/setlocale.md) wirkt sich nicht auf das C++-Standardbibliothek Gebietsschema angegeben, alle C++-Standardbibliothek Objekte weiterhin verwenden, das Gebietsschema "C".  
  
```cpp  
// multithread_locale_1.cpp  
// compile with: /EHsc /MD  
#include <clocale>  
#include <cstdio>  
#include <locale>  
#include <process.h>  
#include <windows.h>  
  
#define NUM_THREADS 2  
using namespace std;  
  
unsigned __stdcall RunThreadA(void *params);  
unsigned __stdcall RunThreadB(void *params);  
  
BOOL localeSet = FALSE;  
HANDLE printMutex = CreateMutex(NULL, FALSE, NULL);  
  
int main()  
{  
    HANDLE threads[NUM_THREADS];  
  
    unsigned aID;  
    threads[0] = (HANDLE)_beginthreadex(  
        NULL, 0, RunThreadA, NULL, 0, &aID);  
  
    unsigned bID;  
    threads[1] = (HANDLE)_beginthreadex(  
        NULL, 0, RunThreadB, NULL, 0, &bID);  
  
    WaitForMultipleObjects(2, threads, TRUE, INFINITE);  
  
    printf_s("[Thread main] Per-thread locale is NOT enabled.\n");  
    printf_s("[Thread main] CRT locale is set to \"%s\"\n",  
        setlocale(LC_ALL, NULL));  
    printf_s("[Thread main] locale::global is set to \"%s\"\n",  
        locale().name().c_str());  
  
    CloseHandle(threads[0]);  
    CloseHandle(threads[1]);  
    CloseHandle(printMutex);  
  
    return 0;  
}  
  
unsigned __stdcall RunThreadA(void *params)  
{  
    _configthreadlocale(_ENABLE_PER_THREAD_LOCALE);  
    setlocale(LC_ALL, "french");  
    localeSet = TRUE;  
  
    WaitForSingleObject(printMutex, INFINITE);  
    printf_s("[Thread A] Per-thread locale is enabled.\n");  
    printf_s("[Thread A] CRT locale is set to \"%s\"\n",  
        setlocale(LC_ALL, NULL));  
    printf_s("[Thread A] locale::global is set to \"%s\"\n\n",  
        locale().name().c_str());  
    ReleaseMutex(printMutex);  
  
    return 1;  
}  
  
unsigned __stdcall RunThreadB(void *params)  
{  
    while (!localeSet)  
        Sleep(100);  
  
    WaitForSingleObject(printMutex, INFINITE);  
    printf_s("[Thread B] Per-thread locale is NOT enabled.\n");  
    printf_s("[Thread B] CRT locale is set to \"%s\"\n",  
        setlocale(LC_ALL, NULL));  
    printf_s("[Thread B] locale::global is set to \"%s\"\n\n",  
        locale().name().c_str());  
    ReleaseMutex(printMutex);  
  
    return 1;  
}  
```  
  
```Output  
[Thread A] Per-thread locale is enabled.  
[Thread A] CRT locale is set to "French_France.1252"  
[Thread A] locale::global is set to "C"  
  
[Thread B] Per-thread locale is NOT enabled.  
[Thread B] CRT locale is set to "C"  
[Thread B] locale::global is set to "C"  
  
[Thread main] Per-thread locale is NOT enabled.  
[Thread main] CRT locale is set to "C"  
[Thread main] locale::global is set to "C"  
```  
  
## <a name="example"></a>Beispiel  
 
In diesem Beispiel erzeugt der Hauptthread zwei untergeordnete Threads. Der erste Thread, Thread A aktiviert threadspezifisches Gebietsschema durch Aufrufen von `_configthreadlocale(_ENABLE_PER_THREAD_LOCALE)`. Der zweite Thread, Thread B als auch den Hauptthread, aktivieren Sie threadspezifisches Gebietsschema nicht. Thread A wird anschließend fortgesetzt wird, so ändern Sie das Gebietsschema mit dem [locale:: Global](../standard-library/locale-class.md#global) -Methode der C++-Standardbibliothek.  
  
Da der Thread ein threadspezifisches Gebietsschema aktiviert ist, nur die C-Laufzeitbibliothek-Funktionen im Thread A Einstieg in das Gebietsschema "Französisch" hat. Die C-Laufzeitbibliothek-Funktionen in Thread B und im Hauptthread weiterhin das Gebietsschema "C" verwenden. Da jedoch die [locale:: Global](../standard-library/locale-class.md#global) Methode ändert das Gebietsschema "Global", alle C++-Standardbibliothek-Objekte in allen Threads zu starten, verwenden das Gebietsschema "Französisch".  
  
```cpp  
// multithread_locale_2.cpp  
// compile with: /EHsc /MD  
#include <clocale>  
#include <cstdio>  
#include <locale>  
#include <process.h>  
#include <windows.h>  
  
#define NUM_THREADS 2  
using namespace std;  
  
unsigned __stdcall RunThreadA(void *params);  
unsigned __stdcall RunThreadB(void *params);  
  
BOOL localeSet = FALSE;  
HANDLE printMutex = CreateMutex(NULL, FALSE, NULL);  
  
int main()  
{  
    HANDLE threads[NUM_THREADS];  
  
    unsigned aID;  
    threads[0] = (HANDLE)_beginthreadex(  
        NULL, 0, RunThreadA, NULL, 0, &aID);  
  
    unsigned bID;  
    threads[1] = (HANDLE)_beginthreadex(  
        NULL, 0, RunThreadB, NULL, 0, &bID);  
  
    WaitForMultipleObjects(2, threads, TRUE, INFINITE);  
  
    printf_s("[Thread main] Per-thread locale is NOT enabled.\n");  
    printf_s("[Thread main] CRT locale is set to \"%s\"\n",  
        setlocale(LC_ALL, NULL));  
    printf_s("[Thread main] locale::global is set to \"%s\"\n",  
        locale().name().c_str());  
  
    CloseHandle(threads[0]);  
    CloseHandle(threads[1]);  
    CloseHandle(printMutex);  
  
    return 0;  
}  
  
unsigned __stdcall RunThreadA(void *params)  
{  
    _configthreadlocale(_ENABLE_PER_THREAD_LOCALE);  
    locale::global(locale("french"));  
    localeSet = TRUE;  
  
    WaitForSingleObject(printMutex, INFINITE);  
    printf_s("[Thread A] Per-thread locale is enabled.\n");  
    printf_s("[Thread A] CRT locale is set to \"%s\"\n",  
        setlocale(LC_ALL, NULL));  
    printf_s("[Thread A] locale::global is set to \"%s\"\n\n",  
        locale().name().c_str());  
    ReleaseMutex(printMutex);  
  
    return 1;  
}  
  
unsigned __stdcall RunThreadB(void *params)  
{  
    while (!localeSet)  
        Sleep(100);  
  
    WaitForSingleObject(printMutex, INFINITE);  
    printf_s("[Thread B] Per-thread locale is NOT enabled.\n");  
    printf_s("[Thread B] CRT locale is set to \"%s\"\n",  
        setlocale(LC_ALL, NULL));  
    printf_s("[Thread B] locale::global is set to \"%s\"\n\n",  
        locale().name().c_str());  
    ReleaseMutex(printMutex);  
  
    return 1;  
}  
```  
  
```Output  
[Thread A] Per-thread locale is enabled.  
[Thread A] CRT locale is set to "French_France.1252"  
[Thread A] locale::global is set to "French_France.1252"  
  
[Thread B] Per-thread locale is NOT enabled.  
[Thread B] CRT locale is set to "C"  
[Thread B] locale::global is set to "French_France.1252"  
  
[Thread main] Per-thread locale is NOT enabled.  
[Thread main] CRT locale is set to "C"  
[Thread main] locale::global is set to "French_France.1252"  
```  
  
## <a name="example"></a>Beispiel  
 
In diesem Beispiel erzeugt der Hauptthread zwei untergeordnete Threads. Der erste Thread, Thread A aktiviert threadspezifisches Gebietsschema durch Aufrufen von `_configthreadlocale(_ENABLE_PER_THREAD_LOCALE)`. Der zweite Thread, Thread B als auch den Hauptthread, aktivieren Sie threadspezifisches Gebietsschema nicht. Thread B wird anschließend so ändern Sie das Gebietsschema mit dem [Setlocale](../preprocessor/setlocale.md) Funktion der C-Laufzeitbibliothek.  
  
Da Thread B keine threadspezifische Gebietsschema aktiviert, starten Sie die C-Laufzeitbibliothek-Funktionen in Thread B und im Hauptthread unter Verwendung des Gebietsschemas "Französisch". Die Funktionen der C-Laufzeitbibliothek in Thread A weiterhin das Gebietsschema "C" zu verwenden, da der Thread ein threadspezifisches Gebietsschema aktiviert hat. Da außerdem [Setlocale](../preprocessor/setlocale.md) wirkt sich nicht auf das C++-Standardbibliothek Gebietsschema angegeben, alle C++-Standardbibliothek Objekte weiterhin verwenden, das Gebietsschema "C".  
  
```cpp  
// multithread_locale_3.cpp  
// compile with: /EHsc /MD  
#include <clocale>  
#include <cstdio>  
#include <locale>  
#include <process.h>  
#include <windows.h>  
  
#define NUM_THREADS 2  
using namespace std;  
  
unsigned __stdcall RunThreadA(void *params);  
unsigned __stdcall RunThreadB(void *params);  
  
BOOL localeSet = FALSE;  
BOOL configThreadLocaleCalled = FALSE;  
HANDLE printMutex = CreateMutex(NULL, FALSE, NULL);  
  
int main()  
{  
    HANDLE threads[NUM_THREADS];  
  
    unsigned aID;  
    threads[0] = (HANDLE)_beginthreadex(  
        NULL, 0, RunThreadA, NULL, 0, &aID);  
  
    unsigned bID;  
    threads[1] = (HANDLE)_beginthreadex(  
        NULL, 0, RunThreadB, NULL, 0, &bID);  
  
    WaitForMultipleObjects(2, threads, TRUE, INFINITE);  
  
    printf_s("[Thread main] Per-thread locale is NOT enabled.\n");  
    printf_s("[Thread main] CRT locale is set to \"%s\"\n",  
        setlocale(LC_ALL, NULL));  
    printf_s("[Thread main] locale::global is set to \"%s\"\n",  
        locale().name().c_str());  
  
    CloseHandle(threads[0]);  
    CloseHandle(threads[1]);  
    CloseHandle(printMutex);  
  
    return 0;  
}  
  
unsigned __stdcall RunThreadA(void *params)  
{  
    _configthreadlocale(_ENABLE_PER_THREAD_LOCALE);  
    configThreadLocaleCalled = TRUE;  
    while (!localeSet)  
        Sleep(100);  
  
    WaitForSingleObject(printMutex, INFINITE);  
    printf_s("[Thread A] Per-thread locale is enabled.\n");  
    printf_s("[Thread A] CRT locale is set to \"%s\"\n",  
        setlocale(LC_ALL, NULL));  
    printf_s("[Thread A] locale::global is set to \"%s\"\n\n",  
        locale().name().c_str());  
    ReleaseMutex(printMutex);  
  
    return 1;  
}  
  
unsigned __stdcall RunThreadB(void *params)  
{  
    while (!configThreadLocaleCalled)  
        Sleep(100);  
    setlocale(LC_ALL, "french");  
    localeSet = TRUE;  
  
    WaitForSingleObject(printMutex, INFINITE);  
    printf_s("[Thread B] Per-thread locale is NOT enabled.\n");  
    printf_s("[Thread B] CRT locale is set to \"%s\"\n",  
        setlocale(LC_ALL, NULL));  
    printf_s("[Thread B] locale::global is set to \"%s\"\n\n",  
        locale().name().c_str());  
    ReleaseMutex(printMutex);  
  
    return 1;  
}  
```  
  
```Output  
[Thread B] Per-thread locale is NOT enabled.  
[Thread B] CRT locale is set to "French_France.1252"  
[Thread B] locale::global is set to "C"  
  
[Thread A] Per-thread locale is enabled.  
[Thread A] CRT locale is set to "C"  
[Thread A] locale::global is set to "C"  
  
[Thread main] Per-thread locale is NOT enabled.  
[Thread main] CRT locale is set to "French_France.1252"  
[Thread main] locale::global is set to "C"  
```  
  
## <a name="example"></a>Beispiel  
 
In diesem Beispiel erzeugt der Hauptthread zwei untergeordnete Threads. Der erste Thread, Thread A aktiviert threadspezifisches Gebietsschema durch Aufrufen von `_configthreadlocale(_ENABLE_PER_THREAD_LOCALE)`. Der zweite Thread, Thread B als auch den Hauptthread, aktivieren Sie threadspezifisches Gebietsschema nicht. Thread B wird anschließend so ändern Sie das Gebietsschema mit dem [locale:: Global](../standard-library/locale-class.md#global) -Methode der C++-Standardbibliothek.  
  
Da Thread B keine threadspezifische Gebietsschema aktiviert, starten Sie die C-Laufzeitbibliothek-Funktionen in Thread B und im Hauptthread unter Verwendung des Gebietsschemas "Französisch". Die Funktionen der C-Laufzeitbibliothek in Thread A weiterhin das Gebietsschema "C" zu verwenden, da der Thread ein threadspezifisches Gebietsschema aktiviert hat. Da jedoch die [locale:: Global](../standard-library/locale-class.md#global) Methode ändert das Gebietsschema "Global", alle C++-Standardbibliothek-Objekte in allen Threads zu starten, verwenden das Gebietsschema "Französisch".  
  
```cpp  
// multithread_locale_4.cpp  
// compile with: /EHsc /MD  
#include <clocale>  
#include <cstdio>  
#include <locale>  
#include <process.h>  
#include <windows.h>  
  
#define NUM_THREADS 2  
using namespace std;  
  
unsigned __stdcall RunThreadA(void *params);  
unsigned __stdcall RunThreadB(void *params);  
  
BOOL localeSet = FALSE;  
BOOL configThreadLocaleCalled = FALSE;  
HANDLE printMutex = CreateMutex(NULL, FALSE, NULL);  
  
int main()  
{  
    HANDLE threads[NUM_THREADS];  
  
    unsigned aID;  
    threads[0] = (HANDLE)_beginthreadex(  
        NULL, 0, RunThreadA, NULL, 0, &aID);  
  
    unsigned bID;  
    threads[1] = (HANDLE)_beginthreadex(  
        NULL, 0, RunThreadB, NULL, 0, &bID);  
  
    WaitForMultipleObjects(2, threads, TRUE, INFINITE);  
  
    printf_s("[Thread main] Per-thread locale is NOT enabled.\n");  
    printf_s("[Thread main] CRT locale is set to \"%s\"\n",  
        setlocale(LC_ALL, NULL));  
    printf_s("[Thread main] locale::global is set to \"%s\"\n",  
        locale().name().c_str());  
  
    CloseHandle(threads[0]);  
    CloseHandle(threads[1]);  
    CloseHandle(printMutex);  
  
    return 0;  
}  
  
unsigned __stdcall RunThreadA(void *params)  
{  
    _configthreadlocale(_ENABLE_PER_THREAD_LOCALE);  
    configThreadLocaleCalled = TRUE;  
    while (!localeSet)  
        Sleep(100);  
  
    WaitForSingleObject(printMutex, INFINITE);  
    printf_s("[Thread A] Per-thread locale is enabled.\n");  
    printf_s("[Thread A] CRT locale is set to \"%s\"\n",  
        setlocale(LC_ALL, NULL));  
    printf_s("[Thread A] locale::global is set to \"%s\"\n\n",  
        locale().name().c_str());  
    ReleaseMutex(printMutex);  
  
    return 1;  
}  
  
unsigned __stdcall RunThreadB(void *params)  
{  
    while (!configThreadLocaleCalled)  
        Sleep(100);  
    locale::global(locale("french"));  
    localeSet = TRUE;  
  
    WaitForSingleObject(printMutex, INFINITE);  
    printf_s("[Thread B] Per-thread locale is NOT enabled.\n");  
    printf_s("[Thread B] CRT locale is set to \"%s\"\n",  
        setlocale(LC_ALL, NULL));  
    printf_s("[Thread B] locale::global is set to \"%s\"\n\n",  
        locale().name().c_str());  
    ReleaseMutex(printMutex);  
  
    return 1;  
}  
```  
  
```Output  
[Thread B] Per-thread locale is NOT enabled.  
[Thread B] CRT locale is set to "French_France.1252"  
[Thread B] locale::global is set to "French_France.1252"  
  
[Thread A] Per-thread locale is enabled.  
[Thread A] CRT locale is set to "C"  
[Thread A] locale::global is set to "French_France.1252"  
  
[Thread main] Per-thread locale is NOT enabled.  
[Thread main] CRT locale is set to "French_France.1252"  
[Thread main] locale::global is set to "French_France.1252"  
```  
  
## <a name="see-also"></a>Siehe auch  

[Multithreadingunterstützung für älteren Code (Visual C++)](../parallel/multithreading-support-for-older-code-visual-cpp.md)   
[_beginthread, _beginthreadex](../c-runtime-library/reference/beginthread-beginthreadex.md)   
[_configthreadlocale](../c-runtime-library/reference/configthreadlocale.md)   
[setlocale](../preprocessor/setlocale.md)   
[Internationalisierung](../c-runtime-library/internationalization.md)   
[Gebietsschema](../c-runtime-library/locale.md)   
[\<Clocale >](../standard-library/clocale.md)   
[\<locale>](../standard-library/locale.md)   
[locale-Klasse](../standard-library/locale-class.md)