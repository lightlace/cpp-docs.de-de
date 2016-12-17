---
title: "Empfehlungen f&#252;r die Wahl zwischen Funktionen und Macros"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "c.functions"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "Funktionen [CRT], kontra Makros"
  - "Makros, kontra Funktionen"
ms.assetid: 18a633d6-cf1c-470c-a649-fa7677473e2b
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Empfehlungen f&#252;r die Wahl zwischen Funktionen und Macros
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die meisten Microsoft\-Laufzeitbibliotheksroutinen werden oder assemblierte Funktionen kompiliert, aber einige Routinen werden als Makros implementiert.  Wenn eine Headerdatei eine Funktion und eine Makroversion einer Routine deklariert, hat die Makrodefinition Vorrang, da diese immer nach der Funktionsdeklaration wird.  Wenn Sie eine Routine aufrufen, als die Funktion und Makro implementiert wird, können Sie den Compiler veranlasst, die Funktionsversion auf zwei Arten verwenden:  
  
-   Schließen Sie den Routinenamen in Klammern ein.  
  
    ```  
    #include <ctype.h>  
    a = _toupper(a);    // Use macro version of toupper.  
    a = (_toupper)(a);  // Force compiler to use   
                        // function version of toupper.  
    ```  
  
-   "Heben Sie" Makrodefinition mit den `#undef`\-Direktive die Definition:  
  
    ```  
    #include <ctype.h>  
    #undef _toupper  
    ```  
  
 Wenn Sie zwischen einer Funktion und eine Makroimplementierung einer Bibliotheksroutine auswählen müssen, sollten folgende Kompromisse:  
  
-   **Speed versus size** Der Hauptvorteil der Anwendung von Makros ist schnelleren Ausführungszeit.  Während des Präprozessorlaufs wird ein \(Makro ersetzt durch ihre Definition\) inline erweitert, wenn sie verwendet wird.  Eine Funktionsdefinition tritt nur einmal und zwar unabhängig davon, wieoft sie aufgerufen wird.  Makros erhöhen möglicherweise Codegröße aber noch nicht den Aufwand, der mit Funktionsaufrufen zugeordnet ist.  
  
-   Funktion A **Function evaluation** ergibt eine Adresse aus; ein Makro jedoch nicht.  So können Sie einen Makronamen in Kontexten nicht verwenden, die einen Zeiger benötigen.  Beispielsweise können Sie einen Zeiger auf eine Funktion, jedoch kein Zeiger deklarieren einem Makro.  
  
-   **Type\-checking**, wenn Sie eine Funktion deklariert, der Compiler kann die Argumenttypen überprüfen.  Da Sie ein Makro nicht deklarieren können, kann der Compiler Makroargumenttypen nicht untersuchen; obwohl die Argumentanzahl überprüfen kann, durchlaufen Sie einem Makro.  
  
## Siehe auch  
 [CRT\-Bibliotheksfunktionen](../c-runtime-library/crt-library-features.md)