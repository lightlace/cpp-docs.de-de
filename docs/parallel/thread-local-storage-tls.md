---
title: Threadlokaler Speicher (TLS)
ms.date: 11/04/2016
helpviewer_keywords:
- multithreading [C++], Thread Local Storage
- TLS [C++]
- threading [C++], Thread Local Storage
- storing thread-specific data
- thread attribute
- Thread Local Storage [C++]
ms.assetid: 80801907-d792-45ca-b776-df0cf2e9f197
ms.openlocfilehash: 5c7bf2ae7cb5bfe71be9a1d72147e97c894064b3
ms.sourcegitcommit: 7d64c5f226f925642a25e07498567df8bebb00d4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2019
ms.locfileid: "65448912"
---
# <a name="thread-local-storage-tls"></a>Threadlokaler Speicher (TLS)

Durch den lokalen Threadspeicher (Thread Local Storage, TLS) kann jeder Thread in einem bestimmten Multithreadprozess Speicherplätze für threadspezifische Daten zuordnen. Dynamisch gebundene (Laufzeit) threadspezifische Daten über die TLS-API unterstützt ([TlsAlloc](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-tlsalloc).  Win32 und Microsoft C++ Compiler konvertiert nun Unterstützung für die (Ladezeit) threadspezifische Daten zusätzlich zu den vorhandenen API-Implementierung statisch gebunden.

##  <a name="_core_compiler_implementation_for_tls"></a> Compilerimplementierung für TLS

**C++11:**  Die `thread_local` -Speicherklassenspezifizierer ist die empfohlene Methode zum Angeben von lokalem Threadspeicher für Objekte und Klassenmember. Weitere Informationen finden Sie unter [Speicherklassen (C++)](../cpp/storage-classes-cpp.md).

Visual C++ bietet auch ein Microsoft-spezifische Attribut [Thread](../cpp/thread.md), als erweiterten Speicherklassenmodifizierer. Verwenden der **__declspec** -Schlüsselwort zu deklarieren, ein **Thread** Variable. Mit folgendem Code wird z. B. eine Ganzzahl-TLS-Variable deklariert und mit einem Wert initialisiert:

```
__declspec( thread ) int tls_i = 1;
```

## <a name="rules-and-limitations"></a>Regeln und Einschränkungen

Die folgenden Richtlinien müssen bei der Deklaration von statisch gebundenen lokalen Threadobjekten und -variablen beachtet werden: Diese Richtlinien gelten für [Thread](../cpp/thread.md)und größtenteils auch mit [Thread_local](../cpp/storage-classes-cpp.md):

- Die **Thread** Attribut kann nur auf Klassen- und Datendeklarationen und-Definitionen angewendet werden. Die Verwendung in Funktionsdeklarationen oder -definitionen ist nicht zulässig. Beispielsweise verursacht der folgende Code einen Compilerfehler:

    ```
    __declspec( thread )void func();     // This will generate an error.
    ```

- Die **Thread** Modifizierer kann angegeben werden, nur für Datenelemente mit **statische** Block. Hierzu zählen globale Datenobjekte (sowohl **statische** und **"extern"**), lokale statische Objekte sowie statische Datenmember von C++-Klassen. Automatische Datenobjekte können nicht deklariert werden, mit der **Thread** Attribut. Im folgenden Code werden Compilerfehler generiert:

    ```
    void func1()
    {
        __declspec( thread )int tls_i;            // This will generate an error.
    }

    int func2(__declspec( thread )int tls_i )    // This will generate an error.
    {
        return tls_i;
    }
    ```

- Deklarationen und die Definitionen eines threadlokalen Objekts alle angeben muss. die **Thread** Attribut. Durch folgenden Code wird z. B. ein Fehler verursacht:

    ```
    #define Thread  __declspec( thread )
    extern int tls_i;        // This will generate an error, since the
    int __declspec( thread )tls_i;        // declaration and definition differ.
    ```

- Die **Thread** Attribut kann nicht als Typmodifizierer verwendet werden. Beispielsweise verursacht der folgende Code einen Compilerfehler:

    ```
    char __declspec( thread ) *ch;        // Error
    ```

- Da die Deklaration von C++, verwenden Objekte die **Thread** Attribut zulässig ist, die folgenden beiden Beispiele semantisch gleichwertig:

    ```
    __declspec( thread ) class B
    {
    // Code
    } BObject;  // OK--BObject is declared thread local.

    class B
    {
    // Code
    };
    __declspec( thread ) B BObject;  // OK--BObject is declared thread local.
    ```

- Die Adresse eines threadlokalen Objekts wird nicht als konstant angesehen und jeder Ausdruck mit einer solchen Adresse wird nicht als konstanter Ausdruck angesehen. In Standard-C bedeutet dies, dass die Verwendung der Adresse einer threadlokalen Variablen als Initialisierer für ein Objekt oder einen Zeiger nicht zulässig ist. Folgender Code wird z. B. vom C-Compiler mit einem Fehlerflag versehen:

    ```
    __declspec( thread )int tls_i;
    int *p = &tls_i;       //This will generate an error in C.
    ```

   Diese Einschränkung gilt nicht für C++. Da C++ die dynamische Initialisierung aller Objekte gestattet, kann ein Objekt mit einem Ausdruck initialisiert werden, der die Adresse einer threadlokalen Variablen verwendet. Die Vorgehensweise ist hierbei identisch mit der Konstruktion eines lokalen Threadobjekts. Durch den zuvor aufgeführten Code wird z. B. kein Fehler generiert, wenn er als C++-Quelldatei kompiliert wird. Beachten Sie, dass die Adresse einer lokalen Threadvariablen nur solange gültig ist, solange der Thread vorhanden ist, aus dem die jeweilige Adresse stammt.

- In Standard-C ist die Initialisierung eines Objekts oder einer Variablen mit einem Ausdruck zulässig, der einen Verweis auf sich selbst enthält. Dies gilt jedoch nur für Objekte, die keinen static-Extent aufweisen. Obwohl in C++ diese Art der dynamischen Initialisierung von Objekten mit einem Ausdruck, der einen Verweis auf sich selbst enthält, normalerweise zulässig ist, ist dies für threadlokale Objekte nicht zutreffend. Zum Beispiel:

    ```
    __declspec( thread )int tls_i = tls_i;                // Error in C and C++
    int j = j;                               // OK in C++, error in C
    __declspec( thread )int tls_i = sizeof( tls_i )       // Legal in C and C++
    ```

   Beachten Sie, dass ein `sizeof`-Ausdruck, der das Objekt enthält, das derzeit initialisiert wird, keinen Verweis auf sich selbst darstellt und sowohl in C als auch in C++ gültig ist.

   In C++ ist diese Art der dynamischen Initialisierung von Threaddaten aufgrund möglicher zukünftiger Verbesserungen der lokalen Threadspeicherfunktion nicht zulässig.

- Unter Windows-Betriebssystemen vor Windows Vista `__declspec`(Thread) weist einige Einschränkungen. Wenn durch eine DLL beliebige Daten oder Objekte als `__declspec` (Thread) deklariert werden, kann beim dynamischen Ladevorgang eine allgemeine Schutzverletzung auftreten. Nach dem Laden der DLL mit [LoadLibrary](/windows/desktop/api/libloaderapi/nf-libloaderapi-loadlibrarya), es Systemausfall verursacht, wenn der Code verweist auf die `__declspec`(Thread)-Daten. Da der globale Variablenspeicher für einen Thread zur Laufzeit reserviert wird, basiert die Größe dieses Speichers auf der Berechnung der Anforderungen der jeweiligen Anwendung sowie der Anforderungen aller DLLs, die statisch gebunden sind. Bei der Verwendung von `LoadLibrary` können Sie diesen Speicher nicht für die threadlokalen Variablen erweitern, die mit `__declspec` (Thread) deklariert wurden. Verwenden Sie die TLS-APIs, wie z. B. [TlsAlloc](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-tlsalloc), in der DLL TLS zuweisen, wenn die DLL geladen werden kann, mit `LoadLibrary`.

## <a name="see-also"></a>Siehe auch

[Multithreading bei C und Win32](multithreading-with-c-and-win32.md)
