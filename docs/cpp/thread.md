---
title: "Thread | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "thread"
  - "thread_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__declspec-Schlüsselwort [C++], Thread"
  - "thread __declspec-Schlüsselwort"
  - "Lokaler Threadspeicher (TLS)"
  - "TLS (lokaler Threadspeicher), Compilerimplementierung"
ms.assetid: 667f2a77-6d1f-4b41-bee8-05e67324fab8
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Thread
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Der erweiterte Speicherklassenmodifizierer **thread** wird verwendet, um einen Thread für eine lokale Variable zu deklarieren.  Verwenden Sie für die portable Entsprechung in C \+\+ 11, den [Thread\_local](../cpp/storage-classes-cpp.md#thread_local) Speicherklassenspezifizierer.  
  
## Syntax  
  
```  
  
__declspec( thread ) declarator  
```  
  
## Hinweise  
 Lokaler Threadspeicher \(TLS\) ist der Mechanismus, mit dem jeder Thread in einem Multithreadprozess den Speicher für threadspezifische Daten zuordnet.  In den standardmäßigen Multithreadprogrammen werden Daten auf allen Threads eines angegebenen Prozesses freigegeben, während der lokale Threadspeicher der Mechanismus zum Zuordnen der threadspezifischen Daten ist.  Eine detaillierte Erläuterung zu Threads finden Sie unter [Multithreading](../parallel/multithreading-support-for-older-code-visual-cpp.md).  
  
 Deklarationen von lokalen Variablen des Threads müssen eine [erweiterte Attributsyntax](../cpp/declspec.md) und das `__declspec`\-Schlüsselwort mit dem **thread**\-Schlüsselwort verwenden.  Mit folgendem Code wird z. B. eine Ganzzahl\-TLS\-Variable deklariert und mit einem Wert initialisiert:  
  
```  
__declspec( thread ) int tls_i = 1;  
```  
  
 Sie müssen diese Richtlinien beachten, wenn Sie lokale Objekte und Variablen eines Threads deklarieren:  
  
-   Sie können das **thread**\-Attribut nur auf Klassen und Datendeklarationen und \-definitionen anwenden. **thread** kann nicht für Funktionsdeklarationen oder \- definitionen verwendet werden.  
  
-   Die Verwendung des **thread**\-Attributs kann mit dem [verzögerten Laden](../build/reference/linker-support-for-delay-loaded-dlls.md) von DLL\-Importen in Konflikt treten**.**  
  
-   Auf XP\-Systemen funktioniert `thread` möglicherweise nicht ordnungsgemäß, wenn eine DLL \_\_declspec\(thread\)\-Daten verwendet und dynamisch über LoadLibrary geladen wird.  
  
-   Sie können das **thread**\-Attribut nur für Datenelemente mit statischer Speicherdauer angeben.  Hierzu zählen globale Datenobjekte \(sowohl **static** als auch `extern`\), lokale statische Objekte sowie statische Datenmember von Klassen.  Sie können automatische Datenobjekte nicht mit dem **thread**\-Attribut deklarieren.  
  
-   Sie müssen das **thread**\-Attribut für die Deklaration und Definition eines lokalen Threadobjekts verwenden, egal ob die Deklaration und Definition in der gleichen Datei oder in separaten Dateien auftreten.  
  
-   Sie können das **thread**\-Attribut nicht als Typmodifizierer verwenden.  
  
-   Da die Deklaration von Objekten, die das **thread**\-Attribut verwenden, zulässig ist, sind diese beiden Beispiele semantisch gleichwertig:  
  
    ```  
    // declspec_thread_2.cpp  
    // compile with: /LD  
    __declspec( thread ) class B {  
    public:  
       int data;  
    } BObject;   // BObject declared thread local.  
  
    class B2 {  
    public:  
       int data;  
    };  
    __declspec( thread ) B2 BObject2;   // BObject2 declared thread local.  
    ```  
  
-   In Standard\-C ist die Initialisierung eines Objekts oder einer Variablen mit einem Ausdruck zulässig, der einen Verweis auf sich selbst enthält. Dies gilt jedoch nur für Objekte, die keinen statischen Wertebereich aufweisen.  Obwohl in C\+\+ diese dynamische Objektinitialisierung mit einem Ausdruck, der einen Verweis auf sich selbst enthält, normalerweise zulässig ist, ist dieser Initialisierungstyp für lokale Threadobjekte nicht zulässig.  Zum Beispiel:  
  
    ```  
    // declspec_thread_3.cpp  
    // compile with: /LD  
    #define Thread __declspec( thread )  
    int j = j;   // Okay in C++; C error  
    Thread int tls_i = sizeof( tls_i );   // Okay in C and C++  
    ```  
  
     Beachten Sie, dass ein `sizeof`\-Ausdruck, der das Objekt enthält, das derzeit initialisiert wird, keinen Verweis auf sich selbst darstellt und sowohl in C als auch in C\+\+ zulässig ist.  
  
 **Ende Microsoft\-spezifisch**  
  
## Siehe auch  
 [\_\_declspec](../cpp/declspec.md)   
 [C\+\+\-Schlüsselwörter](../cpp/keywords-cpp.md)   
 [Lokaler Threadspeicher \(TLS\)](../parallel/thread-local-storage-tls.md)