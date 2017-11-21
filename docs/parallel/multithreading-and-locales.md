---
title: Multithreading und Gebietsschemas | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- locales [C++], multithreading
- multithreading [C++], locales
- threading [C++], locales
- per-thread locale
ms.assetid: d6fb159a-eaca-4130-a51a-f95d62f71485
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 2e60083aa67cc640dafb5c096b83d3097df04db1
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="multithreading-and-locales"></a>Multithreading und Gebietsschemas
C-Laufzeitbibliothek und C++-Standardbibliothek bieten Unterstützung für das Gebietsschema des Programms ändern. Dieses Thema behandelt Probleme, die auftreten, wenn die Gebietsschema-Funktionen der beiden Bibliotheken in einer Multithreadanwendung zu verwenden.  
  
## <a name="remarks"></a>Hinweise  
 Mit der C-Laufzeitbibliothek können Sie mithilfe von Multithreadanwendungen erstellen die `_beginthread` und `_beginthreadex` Funktionen. Dieses Thema behandelt nur Multithread-Anwendungen die Verwendung dieser Funktionen erstellt. Weitere Informationen finden Sie unter [_beginthread, _beginthreadex](../c-runtime-library/reference/beginthread-beginthreadex.md).  
  
 Um das Gebietsschema bei Verwendung von C-Laufzeitbibliothek zu ändern, verwenden die [Setlocale](../preprocessor/setlocale.md) Funktion. In früheren Versionen von Visual C++ würden diese Funktion immer das Gebietsschema der gesamten Anwendung ändern. Es gibt unterstützt jetzt legen Sie das Gebietsschema auf Basis pro Thread. Dies erfolgt mithilfe der [_configthreadlocale](../c-runtime-library/reference/configthreadlocale.md) Funktion. Um anzugeben, dass [Setlocale](../preprocessor/setlocale.md) sollten nur ändern, das Gebietsschema im aktuellen Thread, Aufruf `_configthreadlocale(_ENABLE_PER_THREAD_LOCALE)` in diesem Thread. Im Gegensatz dazu aufrufen `_configthreadlocale(_DISABLE_PER_THREAD_LOCALE)` führt dazu, dass Thread das globale Gebietsschema verwendet, und jeder Aufruf von [Setlocale](../preprocessor/setlocale.md) auf, als Thread des Gebietsschemas in allen Threads geändert werden, die nicht explizit threadspezifische Gebietsschema aktiviert haben.  
  
 Um das Gebietsschema bei Verwendung der C++-Laufzeitbibliothek zu ändern, verwenden die [Locale-Klasse](../standard-library/locale-class.md). Durch Aufrufen der [Locale](../standard-library/locale-class.md#global) -Methode, ändern Sie das Gebietsschema in allen Threads, die nicht explizit threadspezifische Gebietsschema aktiviert ist. Um das Gebietsschema in einem einzigen Thread oder Teil einer Anwendung zu ändern, erstellen Sie eine Instanz von einem `locale` Objekt in diesem Thread oder ein Teil des Codes.  
  
> [!NOTE]
>  Aufrufen von [Locale](../standard-library/locale-class.md#global) ändert das Gebietsschema für die C++-Standardbibliothek und die C-Laufzeitbibliothek. Bei Aufruf [Setlocale](../preprocessor/setlocale.md) ändert nur das Gebietsschema für die C-Laufzeitbibliothek; der C++-Standardbibliothek wird nicht beeinflusst.  
  
 Den folgenden Beispielen wird veranschaulicht, wie Sie die [Setlocale](../preprocessor/setlocale.md) -Funktion, die [Locale-Klasse](../standard-library/locale-class.md), und die [_configthreadlocale](../c-runtime-library/reference/configthreadlocale.md) Funktion das Gebietsschema einer Anwendung in ändern mehrere verschiedene Szenarien.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel erzeugt die Hauptthread zwei untergeordnete Threads. Der erste Thread, Thread A, ermöglicht threadspezifisches Gebietsschema durch Aufrufen von `_configthreadlocale(_ENABLE_PER_THREAD_LOCALE)`. Vom zweiten Thread, Thread B als auch den Hauptthread aktiviere threadspezifisches Gebietsschema nicht. Thread eine anschließend so ändern Sie das Gebietsschema mit der [Setlocale](../preprocessor/setlocale.md) Funktion der C-Laufzeitbibliothek.  
  
 Da Thread ein threadspezifisches Gebietsschema aktiviert ist, nur die C-Laufzeitbibliothek-Funktionen in Thread A beginnen, verwenden das Gebietsschema "Französisch" aufweist. Die C-Laufzeitbibliothek-Funktionen in Thread B und im Hauptthread weiterhin das Gebietsschema "C" verwenden. Darüber hinaus seit [Setlocale](../preprocessor/setlocale.md) wirkt sich nicht auf das C++-Standardbibliothek Gebietsschema angegeben, alle C++-Standardbibliothek Objekte weiterhin das Gebietsschema "C" verwenden.  
  
```  
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
 In diesem Beispiel erzeugt die Hauptthread zwei untergeordnete Threads. Der erste Thread, Thread A, ermöglicht threadspezifisches Gebietsschema durch Aufrufen von `_configthreadlocale(_ENABLE_PER_THREAD_LOCALE)`. Vom zweiten Thread, Thread B als auch den Hauptthread aktiviere threadspezifisches Gebietsschema nicht. Thread eine anschließend so ändern Sie das Gebietsschema mit der [Locale](../standard-library/locale-class.md#global) Methode der C++-Standardbibliothek.  
  
 Da Thread ein threadspezifisches Gebietsschema aktiviert ist, nur die C-Laufzeitbibliothek-Funktionen in Thread A beginnen, verwenden das Gebietsschema "Französisch" aufweist. Die C-Laufzeitbibliothek-Funktionen in Thread B und im Hauptthread weiterhin das Gebietsschema "C" verwenden. Da jedoch die [Locale](../standard-library/locale-class.md#global) Methode ändert das Gebietsschema "Global", alle C++-Standardbibliothek Objekte in allen Threads Einstieg in das Gebietsschema "Französisch".  
  
```  
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
 In diesem Beispiel erzeugt die Hauptthread zwei untergeordnete Threads. Der erste Thread, Thread A, ermöglicht threadspezifisches Gebietsschema durch Aufrufen von `_configthreadlocale(_ENABLE_PER_THREAD_LOCALE)`. Vom zweiten Thread, Thread B als auch den Hauptthread aktiviere threadspezifisches Gebietsschema nicht. Thread B wird anschließend das Gebietsschema mit der [Setlocale](../preprocessor/setlocale.md) Funktion der C-Laufzeitbibliothek.  
  
 Da Thread B kein threadspezifische Gebietsschema aktiviert ist, beginnt die C-Laufzeitbibliothek-Funktionen in Thread B und im Hauptthread an, mit dem Gebietsschema "Französisch". Die Funktionen der C-Laufzeitbibliothek in Thread A weiterhin das Gebietsschema "C" verwenden, da Thread ein threadspezifisches Gebietsschema aktiviert wurde. Darüber hinaus seit [Setlocale](../preprocessor/setlocale.md) wirkt sich nicht auf das C++-Standardbibliothek Gebietsschema angegeben, alle C++-Standardbibliothek Objekte weiterhin das Gebietsschema "C" verwenden.  
  
```  
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
 In diesem Beispiel erzeugt die Hauptthread zwei untergeordnete Threads. Der erste Thread, Thread A, ermöglicht threadspezifisches Gebietsschema durch Aufrufen von `_configthreadlocale(_ENABLE_PER_THREAD_LOCALE)`. Vom zweiten Thread, Thread B als auch den Hauptthread aktiviere threadspezifisches Gebietsschema nicht. Thread B wird anschließend das Gebietsschema mit der [Locale](../standard-library/locale-class.md#global) Methode der C++-Standardbibliothek.  
  
 Da Thread B kein threadspezifische Gebietsschema aktiviert ist, beginnt die C-Laufzeitbibliothek-Funktionen in Thread B und im Hauptthread an, mit dem Gebietsschema "Französisch". Die Funktionen der C-Laufzeitbibliothek in Thread A weiterhin das Gebietsschema "C" verwenden, da Thread ein threadspezifisches Gebietsschema aktiviert wurde. Da jedoch die [Locale](../standard-library/locale-class.md#global) Methode ändert das Gebietsschema "Global", alle C++-Standardbibliothek Objekte in allen Threads Einstieg in das Gebietsschema "Französisch".  
  
```  
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