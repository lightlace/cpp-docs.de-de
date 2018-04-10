---
title: Übersicht über die Dateiübersetzung | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-language
ms.tgt_pltfrm: ''
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- file translation [C++], about file translation
- translation [C++]
- translation phases
- files [C++], translation
- programs [C++], lexical conventions of
- preprocessing translation phase
ms.assetid: 5036c7b7-ccff-4e2c-b052-a9ea6c71af87
caps.latest.revision: 6
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a088d2da30aa77f477f3f6e5064b6b98170e953b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="overview-of-file-translation"></a>Übersicht über die Dateiübersetzung
C++-Programme wie C-Programme bestehen aus mindestens einer Datei. Jede dieser Dateien wird in der folgenden konzeptionellen Reihenfolge übersetzt (die tatsächliche Reihenfolge folgt der "als ob"-Regel: Übersetzung muss so erfolgen, als wären diese Schritte befolgt worden):  
  
1.  Lexikalische Tokenisierung. Zeichenzuordnung und Trigraphverarbeitung, Splicing von Zeilen und Tokenisierung werden in dieser Übersetzungsphase ausgeführt.  
  
2.  Vorverarbeitung. Diese übersetzungsphase bringt Hilfsdateien Quelldateien verweist `#include` Direktiven "Zeichenfolgen" und "eingebracht"-Direktiven behandelt und werden token eingefügt und Makros erweitert (finden Sie unter [Präprozessordirektiven](../preprocessor/preprocessor-directives.md) in der *Präprozessorreferenz* für Weitere Informationen). Das Ergebnis der Vorverarbeitungsphase ist eine Sequenz von Token, die zusammen eine "Übersetzungseinheit" definieren.  
  
     Präprozessordirektiven beginnen immer mit dem Nummernzeichen (**#**) Zeichen (d. h. das erste Zeichen von Leerraum in der Zeile muss ein Nummernzeichen sein). In einer angegebenen Zeile kann nur eine Präprozessoranweisung stehen. Zum Beispiel:  
  
    ```  
    #include <iostream>  // Include text of iostream in   
                         //  translation unit.  
    #define NDEBUG       // Define NDEBUG (NDEBUG contains empty   
                         //  text string).  
    ```  
  
3.  Codegenerierung. Diese Übersetzungsphase verwendet die Token, die in der Vorverarbeitungsphase zum Generieren von Objektcode generiert wurden.  
  
     Während dieser Phase wird die syntaktische und semantische Prüfung des Quellcodes ausgeführt.  
  
 Finden Sie unter [Phasen der Übersetzung](../preprocessor/phases-of-translation.md) in der *Präprozessorreferenz* für Weitere Informationen.  
  
 Der C++-Präprozessor ist eine strikte Obermenge des ANSI C-Präprozessors, aber der C++-Präprozessor unterscheidet sich in mehreren Instanzen. Die folgende Liste beschreibt mehrere Unterschiede zwischen den ANSI C- und den C++-Präprozessoren:  
  
-   Einzeilige Kommentare werden unterstützt. Finden Sie unter [Kommentare](../cpp/comments-cpp.md) für Weitere Informationen.  
  
-   Ein vordefiniertes Makro **__cplusplus**, nur für C++ definiert ist. Finden Sie unter [vordefinierte Makros](../preprocessor/predefined-macros.md) in der *Präprozessorreferenz* für Weitere Informationen.  
  
-   Der C-Präprozessor erkennt die C++-Operatoren nicht: **.\*** ,  **-> \*** , und `::`. Finden Sie unter [Operatoren](../cpp/cpp-built-in-operators-precedence-and-associativity.md) und [Ausdrücke](../cpp/expressions-cpp.md), Weitere Informationen zu Operatoren.  
  
## <a name="see-also"></a>Siehe auch  
 [Lexikalische Konventionen](../cpp/lexical-conventions.md)