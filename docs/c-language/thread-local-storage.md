---
title: "Lokaler Threadspeicher | Microsoft Docs"
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
  - "Speicher, Lokaler Threadspeicher"
  - "Thread-Speicherklassenattribut"
  - "Lokaler Threadspeicher"
  - "Lokale Threadvariablen"
  - "TLS (lokaler Threadspeicher)"
ms.assetid: a0f1b109-c953-4079-aa10-e47f5483173d
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# Lokaler Threadspeicher
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Der lokale Threadspeicher \(TLS\) ist der Mechanismus, mit dem jeder Thread in einem Multithreadprozess den Speicher für threadspezifische Daten zuordnet.  In den standardmäßigen Multithreadprogrammen werden Daten auf allen Threads eines angegebenen Prozesses freigegeben, während der lokale Threadspeicher der Mechanismus zum Zuordnen der threadspezifischen Daten ist.  Eine vollständige Erörterung der Threads finden Sie im [!INCLUDE[winsdkshort](../atl/reference/includes/winsdkshort_md.md)] unter [Threads und Prozesse](http://msdn.microsoft.com/library/windows/desktop/ms684841).  
  
 Die Microsoft\-Programmiersprache C schließt das erweiterte Speicherklassenattribut, thread, mit ein, das mit dem \_\_declspec\-Schlüsselwort verwendet wird, um einen threadlokale Variable zu deklarieren.  Mit folgendem Code wird z. B. eine Ganzzahl\-TLS\-Variable deklariert und mit einem Wert initialisiert:  
  
```  
__declspec( thread ) int tls_i = 1;  
```  
  
 Diese Richtlinien müssen bei der Deklaration von statisch gebundenen threadlokalen Variablen beachtet werden:  
  
-   Die Verwendung von **\_\_declspec\(thread\)** kann mit dem [verzögerten Laden](../build/reference/linker-support-for-delay-loaded-dlls.md) von DLL\-Importen in Konflikt treten**.**  
  
-   Sie können das Threadattribut nur auf Datendeklarationen und \-definitionen anwenden.  Die Verwendung in Funktionsdeklarationen oder \-definitionen ist nicht zulässig.  Beispielsweise verursacht der folgende Code einen Compilerfehler:  
  
    ```  
    #define Thread   __declspec( thread )  
    Thread void func();      /* Error */  
    ```  
  
-   Sie können das thread\-Attribut nur für Datenelemente mit statischer Speicherdauer angeben.  Hierzu zählen globale Daten \(statisch und extern\) und lokale statische Daten.  Sie können automatische Daten nicht mit dem thread\-Attribut deklarieren.  Beispielsweise verursacht der folgende Code Compilerfehler:  
  
    ```  
    #define Thread   __declspec( thread )  
    void func1()  
    {  
        Thread int tls_i;            /* Error */  
    }  
  
    int func2( Thread int tls_i )    /* Error */  
    {  
       return tls_i;  
    }  
    ```  
  
-   Sie müssen das thread\-Attribut für die Deklaration und Definition von threadlokale Daten verwenden, unabhängig davon, ob die Deklaration und Definition in der gleichen Datei oder in separaten Dateien auftreten.  Durch folgenden Code wird z. B. ein Fehler verursacht:  
  
    ```  
    #define Thread   __declspec( thread )  
    extern int tls_i;     /* This generates an error, because the   */  
    int Thread tls_i;     /* declaration and the definition differ. */  
    ```  
  
-   Sie können das thread\-Attribut nicht als Typmodifizierer verwenden.  Beispielsweise verursacht der folgende Code einen Compilerfehler:  
  
    ```  
    char *ch __declspec( thread );      /* Error */  
    ```  
  
-   Die Adresse einer threadlokalen Variablen wird nicht als konstant angesehen und jeder Ausdruck mit einer solchen Adresse nicht als konstanter Ausdruck.  Dies bedeutet, dass Sie die Adresse einer threadlokalen Variablen nicht als Initialisierer für einen Zeiger verwenden können.  Folgender Code wird z. B. vom Compiler mit einem Fehlerflag versehen:  
  
    ```  
    #define Thread   __declspec( thread )  
    Thread int tls_i;  
    int *p = &tls_i;      /* Error */  
    ```  
  
-   In C ist die Initialisierung einer Variablen mit einem Ausdruck zulässig, der einen Verweis auf sich selbst enthält. Dies gilt jedoch nur für Objekte, die keinen statischen Wertebereich aufweisen.  Zum Beispiel:  
  
    ```  
    #define Thread   __declspec( thread )  
    Thread int tls_i = tls_i;             /* Error */  
    int j = j;                            /* Error */  
    Thread int tls_i = sizeof( tls_i )    /* Okay  */  
    ```  
  
     Beachten Sie, dass ein sizeof\-Ausdruck, der die Variable enthält, die derzeit initialisiert wird, keinen Verweis auf sich selbst darstellt und zulässig ist.  
  
-   Die Verwendung von **\_\_declspec\(thread\)** kann mit dem [verzögerten Laden](../build/reference/linker-support-for-delay-loaded-dlls.md) von DLL\-Importen in Konflikt treten**.**  
  
 Weitere Informationen zur Verwendung des Threadattributs finden Sie unter [Multithreading](../parallel/multithreading-support-for-older-code-visual-cpp.md).  
  
 **Ende Microsoft\-spezifisch**  
  
## Siehe auch  
 [C\-Speicherklassenattribute \(erweitert\)](../c-language/c-extended-storage-class-attributes.md)