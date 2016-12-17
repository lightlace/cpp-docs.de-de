---
title: "&#220;bersicht &#252;ber die Datei&#252;bersetzung"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Dateiübersetzung [C++], Informationen über die Dateiübersetzung"
  - "Dateien [C++], Verschiebung"
  - "Phase der Vorverarbeitung der Übersetzung"
  - "Programme [C++], Lexikalische Konventionen von"
  - "Übersetzung [C++]"
  - "Übersetzungsphasen"
ms.assetid: 5036c7b7-ccff-4e2c-b052-a9ea6c71af87
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# &#220;bersicht &#252;ber die Datei&#252;bersetzung
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

C\+\+\-Programme wie C\-Programme bestehen aus mindestens einer Datei.  Jede dieser Dateien wird in der folgenden konzeptionellen Reihenfolge übersetzt \(die tatsächliche Reihenfolge folgt der "als ob"\-Regel: Übersetzung muss so erfolgen, als wären diese Schritte befolgt worden\):  
  
1.  Lexikalische Tokenisierung.  Zeichenzuordnung und Trigraphverarbeitung, Splicing von Zeilen und Tokenisierung werden in dieser Übersetzungsphase ausgeführt.  
  
2.  Vorverarbeitung.  In dieser Übersetzungsphase werden zusätzliche Quelldateien eingebracht, auf die von `#include`\-Direktiven verwiesen wird, es werden "Zeichenfolgen"\- und "Zeichen"\-Direktiven behandelt, und es werden Token eingefügt und Makros erweitert \(weitere Informationen finden Sie in den [Präprozessordirektiven](../preprocessor/preprocessor-directives.md) unter *Präprozessorreferenz*\).  Das Ergebnis der Vorverarbeitungsphase ist eine Sequenz von Token, die zusammen eine "Übersetzungseinheit" definieren.  
  
     Präprozessordirektiven beginnen immer mit dem Nummernzeichen \(**\#**\) \(also muss das erste Nicht\-Leerzeichen in der Zeile ein Nummernzeichen sein\).  In einer angegebenen Zeile kann nur eine Präprozessordirektive stehen.  Beispiel:  
  
    ```  
    #include <iostream>  // Include text of iostream in   
                         //  translation unit.  
    #define NDEBUG       // Define NDEBUG (NDEBUG contains empty   
                         //  text string).  
    ```  
  
3.  Codegenerierung.  Diese Übersetzungsphase verwendet die Token, die in der Vorverarbeitungsphase zum Generieren von Objektcode generiert wurden.  
  
     Während dieser Phase wird die syntaktische und semantische Prüfung des Quellcodes ausgeführt.  
  
 Weitere Informationen erhalten Sie unter [Phasen der Übersetzung](../preprocessor/phases-of-translation.md) in der *Präprozessorreferenz*.  
  
 Der C\+\+\-Präprozessor ist eine strikte Obermenge des ANSI C\-Präprozessors, aber der C\+\+\-Präprozessor unterscheidet sich in mehreren Instanzen.  Die folgende Liste beschreibt mehrere Unterschiede zwischen den ANSI C\- und den C\+\+\-Präprozessoren:  
  
-   Einzeilige Kommentare werden unterstützt.  Weitere Informationen finden Sie unter [Kommentare](../cpp/comments-cpp.md).  
  
-   Ein vordefiniertes Makro, **\_\_cplusplus**, wird nur für C\+\+ definiert.  Weitere Informationen finden Sie unter [Vordefinierte Makros](../preprocessor/predefined-macros.md) in der *Präprozessorreferenz*.  
  
-   Der C\-Präprozessor erkennt die C\+\+\-Operatoren **.\***, **–\>\*** und `::` nicht.  Weitere Informationen zu Operatoren finden Sie unter [Operatoren](../cpp/cpp-built-in-operators-precedence-and-associativity.md) und [Ausdrücke](../cpp/expressions-cpp.md).  
  
## Siehe auch  
 [Lexikalische Konventionen](../cpp/lexical-conventions.md)