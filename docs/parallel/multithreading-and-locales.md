---
title: "Multithreading und Gebietsschemas | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Gebietsschemas [C++], Multithreading"
  - "Multithreading [C++], Gebietsschemas"
  - "Threadspezifisches Gebietsschema"
  - "Threading [C++], Gebietsschemas"
ms.assetid: d6fb159a-eaca-4130-a51a-f95d62f71485
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Multithreading und Gebietsschemas
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Sowohl die C\-Laufzeitbibliothek als auch die C\+\+\-Standardbibliothek unterstützen eine Änderung des Gebietsschemas für ein Programm.  In diesem Thema werden die Fragen behandelt, die beim Verwenden der Gebietsschemafunktionalität der beiden Bibliotheken in einer Multithreadanwendung aufkommen.  
  
## Hinweise  
 Mit der C\-Laufzeitbibliothek lassen sich Multithreadanwendungen mithilfe der `_beginthread`\-Funktion und der `_beginthreadex`\-Funktion erstellen.  Dieses Thema behandelt nur Multithreadanwendungen, die mit diesen Funktionen erstellt wurden.  Weitere Informationen finden Sie unter [\_beginthread, \_beginthreadex](../c-runtime-library/reference/beginthread-beginthreadex.md).  
  
 Um das Gebietsschema bei Verwendung der C\-Laufzeitbibliothek zu ändern, verwenden Sie die [setlocale](../preprocessor/setlocale.md)\-Funktion.  In früheren Versionen von [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] wurde mit dieser Funktion immer das Gebietsschema der gesamten Anwendung geändert.  Ab sofort können Sie das Gebietsschema auch für jeden Thread einzeln festlegen.  Verwenden Sie dazu die [\_configthreadlocale](../c-runtime-library/reference/configthreadlocale.md)\-Funktion.  Um anzugeben, dass [setlocale](../preprocessor/setlocale.md) nur das Gebietsschema im aktuellen Thread ändern soll, rufen Sie in diesem Thread `_configthreadlocale(_ENABLE_PER_THREAD_LOCALE)` auf.  Umgekehrt wird beim Aufruf von `_configthreadlocale(_DISABLE_PER_THREAD_LOCALE)` für den Thread das globale Gebietsschema verwendet. Jeder Aufruf an [setlocale](../preprocessor/setlocale.md) in diesem Thread führt jetzt zu einer Änderung des Gebietsschemas in allen Threads, für die das threadspezifische Gebietsschema nicht explizit aktiviert ist.  
  
 Um das Gebietsschema bei Verwendung der C\+\+\-Laufzeitbibliothek zu ändern, verwenden Sie [locale\-Klasse](../standard-library/locale-class.md).  Durch Aufrufen der [locale::global](../Topic/locale::global.md)\-Methode können Sie das Gebietsschema in allen Threads ändern, für die das threadspezifische Gebietsschema nicht explizit aktiviert ist.  Um das Gebietsschema in einem einzelnen Thread oder in einem bestimmten Codeabschnitt einer Anwendung zu ändern, erstellen Sie eine Instanz eines `locale`\-Objekts in dem jeweiligen Thread bzw. Codeabschnitt.  
  
> [!NOTE]
>  Durch Aufrufen von [locale::global](../Topic/locale::global.md) wird sowohl das Gebietsschema für die C\+\+\-Standardbibliothek als auch für die C\-Laufzeitbibliothek geändert.  Wenn Sie hingegen [setlocale](../preprocessor/setlocale.md) aufrufen, wird nur die C\-Laufzeitbibliothek geändert; die C\+\+\-Standardbibliothek ist davon nicht betroffen.  
  
 Das folgende Beispiel zeigt, wie Sie die [setlocale](../preprocessor/setlocale.md)\-Funktion, die [locale\-Klasse](../standard-library/locale-class.md) und die [\_configthreadlocale](../c-runtime-library/reference/configthreadlocale.md)\-Funktion verwenden, um das Gebietsschema einer Anwendung in verschiedenen Szenarien zu ändern.  
  
## Beispiel  
 In diesem Beispiel werden im Hauptthread zwei untergeordnete Threads erzeugt.  Im ersten Thread, Thread A, wird das threadspezifische Gebietsschema durch Aufrufen von `_configthreadlocale(_ENABLE_PER_THREAD_LOCALE)` aktiviert.  Für den zweiten Thread, Thread B, und den Hauptthread wird kein threadspezifisches Gebietsschema aktiviert.  In Thread A wird anschließend das Gebietsschema mit der [setlocale](../preprocessor/setlocale.md)\-Funktion der C\-Laufzeitbibliothek geändert.  
  
 Da für Thread A das threadspezifische Gebietsschema aktiviert ist, verwenden nur die Funktionen der C\-Laufzeitbibliothek in Thread A ab sofort das Gebietsschema "Französisch".  Die Funktionen der C\-Laufzeitbibliothek in Thread B und im Hauptthread verwenden weiterhin das Gebietsschema "C".  Da zudem [setlocale](../preprocessor/setlocale.md) keine Auswirkungen auf das Gebietsschema der C\+\+\-Standardbibliothek hat, verwenden alle Objekte der C\+\+\-Standardbibliothek weiterhin das Gebietsschema "C".  
  
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
  
  **\[Thread A\] Threadspezifisches Gebietsschema ist aktiviert.**  
**\[Thread A\] CRT\-Gebietsschema wird auf "French\_France.1252" festgelegt**  
**\[Thread A\] locale::global wird auf "C" festgelegt**  
**\[Thread B\] Threadspezifisches Gebietsschema ist NICHT aktiviert.**  
**\[Thread B\] CRT\-Gebietsschema wird auf "C" festgelegt**  
**\[Thread B\] locale::global wird auf "C" festgelegt**  
**\[Thread main\] Threadspezifisches Gebietsschema ist NICHT aktiviert.**  
**\[Thread main\] CRT\-Gebietsschema wird auf "C" festgelegt**  
**\[Thread main\] locale::global wird auf "C" festgelegt**   
## Beispiel  
 In diesem Beispiel werden im Hauptthread zwei untergeordnete Threads erzeugt.  Im ersten Thread, Thread A, wird das threadspezifische Gebietsschema durch Aufrufen von `_configthreadlocale(_ENABLE_PER_THREAD_LOCALE)` aktiviert.  Für den zweiten Thread, Thread B, und den Hauptthread wird kein threadspezifisches Gebietsschema aktiviert.  In Thread A wird anschließend das Gebietsschema mit der [locale::global](../Topic/locale::global.md)\-Methode der C\+\+\-Standardbibliothek geändert.  
  
 Da für Thread A das threadspezifische Gebietsschema aktiviert ist, verwenden nur die Funktionen der C\-Laufzeitbibliothek in Thread A ab sofort das Gebietsschema "Französisch".  Die Funktionen der C\-Laufzeitbibliothek in Thread B und im Hauptthread verwenden weiterhin das Gebietsschema "C".  Da die [locale::global](../Topic/locale::global.md)\-Methode das Gebietsschema jedoch "global" ändert, verwenden alle Objekte der C\+\+\-Standardbibliothek ab sofort das Gebietsschema "Französisch".  
  
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
  
  **\[Thread A\] Threadspezifisches Gebietsschema ist aktiviert.**  
**\[Thread A\] CRT\-Gebietsschema wird auf "French\_France.1252" festgelegt**  
**\[Thread A\] locale::global wird auf "French\_France.1252" festgelegt**  
**\[Thread B\] Threadspezifisches Gebietsschema ist NICHT aktiviert.**  
**\[Thread B\] CRT\-Gebietsschema wird auf "C" festgelegt**  
**\[Thread B\] locale::global wird auf "French\_France.1252" festgelegt**  
**\[Thread main\] Threadspezifisches Gebietsschema ist NICHT aktiviert.**  
**\[Thread main\] CRT\-Gebietsschema wird auf "C" festgelegt**  
**\[Thread main\] locale::global wird auf "French\_France.1252" festgelegt**   
## Beispiel  
 In diesem Beispiel werden im Hauptthread zwei untergeordnete Threads erzeugt.  Im ersten Thread, Thread A, wird das threadspezifische Gebietsschema durch Aufrufen von `_configthreadlocale(_ENABLE_PER_THREAD_LOCALE)` aktiviert.  Für den zweiten Thread, Thread B, und den Hauptthread wird kein threadspezifisches Gebietsschema aktiviert.  In Thread B wird anschließend das Gebietsschema mit der [setlocale](../preprocessor/setlocale.md)\-Funktion der C\-Laufzeitbibliothek geändert.  
  
 Da für Thread B das threadspezifische Gebietsschema deaktiviert ist, verwenden die Funktionen der C\-Laufzeitbibliothek in Thread B und im Hauptthread ab sofort das Gebietsschema "Französisch".  Da für Thread A das threadspezifische Gebietsschema aktiviert ist, verwenden die Funktionen der C\-Laufzeitbibliothek in Thread A weiterhin das Gebietsschema "C".  Da zudem [setlocale](../preprocessor/setlocale.md) keine Auswirkungen auf das Gebietsschema der C\+\+\-Standardbibliothek hat, verwenden alle Objekte der C\+\+\-Standardbibliothek weiterhin das Gebietsschema "C".  
  
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
  
  **\[Thread B\] Threadspezifisches Gebietsschema ist NICHT aktiviert.**  
**\[Thread B\] CRT\-Gebietsschema wird auf "French\_France.1252" festgelegt**  
**\[Thread B\] locale::global wird auf "C" festgelegt**  
**\[Thread A\] Threadspezifisches Gebietsschema ist aktiviert.**  
**\[Thread A\] CRT\-Gebietsschema wird auf "C" festgelegt**  
**\[Thread A\] locale::global wird auf "C" festgelegt**  
**\[Thread main\] Threadspezifisches Gebietsschema ist NICHT aktiviert.**  
**\[Thread main\] CRT\-Gebietsschema wird auf "French\_France.1252" festgelegt**  
**\[Thread main\] locale::global wird auf "C" festgelegt**   
## Beispiel  
 In diesem Beispiel werden im Hauptthread zwei untergeordnete Threads erzeugt.  Im ersten Thread, Thread A, wird das threadspezifische Gebietsschema durch Aufrufen von `_configthreadlocale(_ENABLE_PER_THREAD_LOCALE)` aktiviert.  Für den zweiten Thread, Thread B, und den Hauptthread wird kein threadspezifisches Gebietsschema aktiviert.  In Thread B wird anschließend das Gebietsschema mit der [locale::global](../Topic/locale::global.md)\-Methode der C\+\+\-Standardbibliothek geändert.  
  
 Da für Thread B das threadspezifische Gebietsschema deaktiviert ist, verwenden die Funktionen der C\-Laufzeitbibliothek in Thread B und im Hauptthread ab sofort das Gebietsschema "Französisch".  Da für Thread A das threadspezifische Gebietsschema aktiviert ist, verwenden die Funktionen der C\-Laufzeitbibliothek in Thread A weiterhin das Gebietsschema "C".  Da die [locale::global](../Topic/locale::global.md)\-Methode das Gebietsschema jedoch "global" ändert, verwenden alle Objekte der C\+\+\-Standardbibliothek ab sofort das Gebietsschema "Französisch".  
  
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
  
  **\[Thread B\] Threadspezifisches Gebietsschema ist NICHT aktiviert.**  
**\[Thread B\] CRT\-Gebietsschema wird auf "French\_France.1252" festgelegt**  
**\[Thread B\] locale::global wird auf "French\_France.1252" festgelegt**  
**\[Thread A\] Threadspezifisches Gebietsschema ist aktiviert.**  
**\[Thread A\] CRT\-Gebietsschema wird auf "C" festgelegt**  
**\[Thread A\] locale::global wird auf "French\_France.1252" festgelegt**  
**\[Thread main\] Threadspezifisches Gebietsschema ist NICHT aktiviert.**  
**\[Thread main\] CRT\-Gebietsschema wird auf "French\_France.1252" festgelegt**  
**\[Thread main\] locale::global wird auf "French\_France.1252" festgelegt**   
## Siehe auch  
 [Multithreadingunterstützung für älteren Code \(Visual C\+\+\)](../parallel/multithreading-support-for-older-code-visual-cpp.md)   
 [\_beginthread, \_beginthreadex](../c-runtime-library/reference/beginthread-beginthreadex.md)   
 [\_configthreadlocale](../c-runtime-library/reference/configthreadlocale.md)   
 [setlocale](../preprocessor/setlocale.md)   
 [Internationalisierung](../c-runtime-library/internationalization.md)   
 [Locale](../c-runtime-library/locale.md)   
 [\<clocale\>](../standard-library/clocale.md)   
 [\<locale\>](../standard-library/locale.md)   
 [locale\-Klasse](../standard-library/locale-class.md)