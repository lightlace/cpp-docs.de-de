---
title: "Lokaler Threadspeicher (TLS) | Microsoft Docs"
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
  - "Multithreading [C++], Lokaler Threadspeicher"
  - "Speichern threadspezifischer Daten"
  - "Threadattribut"
  - "Lokaler Threadspeicher [C++]"
  - "Threading [C++], Lokaler Threadspeicher"
  - "TLS [C++]"
ms.assetid: 80801907-d792-45ca-b776-df0cf2e9f197
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# Lokaler Threadspeicher (TLS)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Durch den lokalen Threadspeicher \(Thread Local Storage, TLS\) kann jeder Thread in einem bestimmten Multithreadprozess Speicherplätze für threadspezifische Daten zuordnen.  Dynamisch gebundene \(Laufzeit\) threadspezifische Daten werden mit der TLS\-API \([TlsAlloc](assetId:///TlsAlloc?qualifyHint=False&autoUpgrade=True), [TlsGetValue](assetId:///TlsGetValue?qualifyHint=False&autoUpgrade=True), [TlsSetValue](assetId:///TlsSetValue?qualifyHint=False&autoUpgrade=True) und [TlsFree](assetId:///TlsFree?qualifyHint=False&autoUpgrade=True)\) unterstützt.  Weitere Informationen zur Implementierung von lokalem Threadspeicher in Windows finden Sie unter [Lokaler Threadspeicher \(Windows\)](https://msdn.microsoft.com/en-us/library/windows/desktop/ms686749\(v=vs.85\).aspx).  Von Win32 und dem Visual C\+\+\-Compiler werden nun neben der bestehenden API\-Implementierung statisch gebundene, auf einzelne Threads bezogene \(Ladezeit\-\) Daten unterstützt.  
  
##  <a name="_core_compiler_implementation_for_tls"></a> Compilerimplementierung für TLS  
 **C \+\+ 11:**  Der `thread_local`\-Speicherklassenspezifizierer ist die empfohlene Methode zum Angeben von lokalem Threadspeicher für Objekte und Klassenmember.  Weitere Informationen finden Sie unter [C\+\+\-Speicherklassen](../cpp/storage-classes-cpp.md#thread_local).  
  
 Visual C\+\+ stellt auch ein Microsoft\-spezifisches Attribut, [Thread](../cpp/thread.md), als erweiterten Speicherklassenmodifizierer bereit.  Verwenden Sie das `__declspec`\-Schlüsselwort zum Deklarieren einer **thread**\-Variable.  Mit folgendem Code wird z. B. eine Ganzzahl\-TLS\-Variable deklariert und mit einem Wert initialisiert:  
  
```  
__declspec( thread ) int tls_i = 1;  
```  
  
## Regeln und Einschränkungen  
 Die folgenden Richtlinien müssen bei der Deklaration von statisch gebundenen lokalen Threadobjekten und \-variablen beachtet werden:  Diese Richtlinien gelten für [Thread](../cpp/thread.md) und größtenteils auch für [thread\_local](../cpp/storage-classes-cpp.md#thread_local):  
  
-   Das `thread`\-Attribut kann nur auf Klassen\- und Datendeklarationen und \-definitionen angewendet werden.  Die Verwendung in Funktionsdeklarationen oder \-definitionen ist nicht zulässig.  Beispielsweise verursacht der folgende Code einen Compilerfehler:  
  
    ```  
  
    __declspec( thread )void func();     // This will generate an error.  
    ```  
  
-   Der `thread`\-Modifizierer kann nur in Datenelementen mit `static`\-Extent angegeben werden.  Hierzu zählen globale Datenobjekte \(sowohl `static` als auch `extern`\), lokale statische Objekte sowie statische Datenmember von C\+\+\-Klassen.  Automatische Datenobjekte können nicht mit dem `thread`\-Attribut deklariert werden.  Im folgenden Code werden Compilerfehler generiert:  
  
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
  
-   In allen Deklarationen und Definitionen eines lokalen Threadobjekts muss das `thread`\-Attribut angegeben werden.  Durch folgenden Code wird z. B. ein Fehler verursacht:  
  
    ```  
    #define Thread  __declspec( thread )  
    extern int tls_i;        // This will generate an error, since the  
    int __declspec( thread )tls_i;        // declaration and definition differ.  
    ```  
  
-   Das `thread`\-Attribut kann nicht als Typmodifizierer verwendet werden.  Beispielsweise verursacht der folgende Code einen Compilerfehler:  
  
    ```  
    char __declspec( thread ) *ch;        // Error  
    ```  
  
-   Da die Deklaration von C\+\+\-Objekten, die das `thread`\-Attribut verwenden, zulässig ist, ist die Semantik der beiden folgenden Beispiele gleichwertig:  
  
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
  
-   Die Adresse eines lokalen Threadobjekts wird nicht als konstant angesehen und jeder Ausdruck mit einer solchen Adresse nicht als konstanter Ausdruck.  In Standard\-C bedeutet dies, dass die Verwendung der Adresse einer lokalen Threadvariablen als Initialisierer für ein Objekt oder einen Zeiger nicht zulässig ist.  Folgender Code wird z. B. vom C\-Compiler mit einem Fehlerflag versehen:  
  
    ```  
  
    __declspec( thread )int tls_i;  
    int *p = &tls_i;       //This will generate an error in C.  
    ```  
  
     Diese Einschränkung gilt nicht für C\+\+.  Da C\+\+ die dynamische Initialisierung aller Objekte gestattet, kann ein Objekt mit einem Ausdruck initialisiert werden, der die Adresse einer lokalen Threadvariablen verwendet.  Die Vorgehensweise ist hierbei identisch mit der Konstruktion eines lokalen Threadobjekts.  Durch den zuvor aufgeführten Code wird z. B. kein Fehler generiert, wenn er als C\+\+\-Quelldatei kompiliert wird.  Beachten Sie, dass die Adresse einer lokalen Threadvariablen nur solange gültig ist, solange der Thread vorhanden ist, aus dem die jeweilige Adresse stammt.  
  
-   In Standard\-C ist die Initialisierung eines Objekts oder einer Variablen mit einem Ausdruck zulässig, der einen Verweis auf sich selbst enthält. Dies gilt jedoch nur für Objekte, die keinen static\-Extent aufweisen.  Obwohl in C\+\+ diese Art der dynamischen Initialisierung von Objekten mit einem Ausdruck, der einen Verweis auf sich selbst enthält, normalerweise zulässig ist, ist dies für lokale Threadobjekte nicht zutreffend.  Zum Beispiel:  
  
    ```  
    __declspec( thread )int tls_i = tls_i;                // Error in C and C++   
    int j = j;                               // OK in C++, error in C  
    __declspec( thread )int tls_i = sizeof( tls_i )       // Legal in C and C++  
    ```  
  
     Beachten Sie, dass ein `sizeof`\-Ausdruck, der das Objekt enthält, das derzeit initialisiert wird, keinen Verweis auf sich selbst darstellt und sowohl in C als auch in C\+\+ gültig ist.  
  
     In C\+\+ ist diese Art der dynamischen Initialisierung von Threaddaten aufgrund möglicher zukünftiger Verbesserungen der lokalen Threadspeicherfunktion nicht zulässig.  
  
-   Unter Windows\-Betriebssystemen vor [!INCLUDE[wiprlhext](../c-runtime-library/reference/includes/wiprlhext_md.md)], weist `__declspec` \(Thread\) einige Einschränkungen auf.  Wenn durch eine DLL beliebige Daten oder Objekte als `__declspec` \(Thread\) deklariert werden, kann beim dynamischen Ladevorgang eine allgemeine Schutzverletzung auftreten.  Nachdem die DLL mit [LoadLibrary](http://msdn.microsoft.com/library/windows/desktop/ms684175) geladen wurde, tritt bei jedem Verweis des Codes auf die`__declspec` \(Thread\)\-Daten ein Systemfehler auf.  Da der globale Variablenspeicher für einen Thread zur Laufzeit reserviert wird, basiert die Größe dieses Speichers auf der Berechnung der Anforderungen der jeweiligen Anwendung sowie der Anforderungen aller DLLs, die statisch gebunden sind.  Bei der Verwendung von `LoadLibrary` können Sie diesen Speicher nicht für die lokalen Threadvariablen erweitern, die mit `__declspec` \(Thread\) deklariert wurden.  Wenn die Möglichkeit besteht, dass die DLL mit `LoadLibrary` geladen wird, verwenden Sie zur Zuweisung von TLS die TLS\-APIs in der DLL, z. B. [TlsAlloc](http://msdn.microsoft.com/library/windows/desktop/ms686801).  
  
## Siehe auch  
 [Multithreading bei C und Win32](../parallel/multithreading-with-c-and-win32.md)   
 [Regeln und Einschränkungen für TLS](../misc/rules-and-limitations-for-tls.md)