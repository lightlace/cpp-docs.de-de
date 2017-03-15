---
title: "C++-Tokens"
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
  - "Analysieren, C++-Token"
  - "Token"
  - "Übersetzungseinheiten"
  - "Leerraum, In C++-Token"
ms.assetid: aa812fd0-6d47-4f3f-aee0-db002ee4d8b9
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# C++-Tokens
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ein Token ist das kleinste Element eines C\+\+\-Programms, das für den Compiler von Bedeutung ist. Der C\+\+\-Parser erkennt folgende Arten von Token: Bezeichner, Schlüsselwörter, Literale, Operatoren, Markierungszeichen und andere Trennzeichen. Ein Stream dieser Token bildet eine Übersetzungseinheit.  
  
 Token werden normalerweise durch *Leerstellen* getrennt. Folgende Elemente können Leerstellen sein:  
  
-   Leerzeichen  
  
-   Horizontale oder vertikale Tabstopps  
  
-   Zeilenumbrüche  
  
-   Seitenvorschübe  
  
-   Kommentare  
  
 Der Parser erkennt Schlüsselwörter, Bezeichner, Literale, Operatoren und Markierungszeichen. Informationen zu bestimmten Tokentypen finden Sie unter [Schlüsselwörter](../cpp/keywords-cpp.md), [Bezeichner](../cpp/identifiers-cpp.md), [Numerisch, Boolean und Zeigerliterale](../cpp/numeric-boolean-and-pointer-literals-cpp.md), [Zeichenfolgen\- und Zeichenliterale](../cpp/string-and-character-literals-cpp.md), [Benutzerdefinierte Literale](../cpp/user-defined-literals-cpp.md), [Integrierte C\+\+\-Operatoren, Rangfolge und Assoziativität](../cpp/cpp-built-in-operators-precedence-and-associativity.md) und [Markierungszeichen](../cpp/punctuators-cpp.md). Leerraum wird ignoriert, es sei denn, er wird benötigt, Token voneinander zu trennen.  
  
 Vorverarbeitungstoken werden in den Vorverarbeitungsphasen verwendet, um den Tokenstream zu generieren, der an den Compiler übergeben wird. Es gibt folgende Kategorien für Vorverarbeitungstoken: Headernamen, Bezeichner, Vorverarbeitungszahlen, Zeichenliterale, Zeichenfolgenliterale, Vorverarbeitungsoperatoren und \-markierungszeichen sowie einzelne Nicht\-Leerraumzeichen, die zu keiner der anderen Kategorien passen. Zeichen\- und Zeichenfolgenliterale können benutzerdefinierte Literale sein. Vorverarbeitungstoken können durch Leerraum oder Kommentare voneinander getrennt werden.  
  
 Der Parser trennt Token vom Eingabestream, indem das längstmögliche Token mithilfe der Eingabezeichen in einer Prüfung von links nach rechts erstellt wird. Betrachten Sie dieses Codefragment:  
  
```  
a = i+++j;  
```  
  
 Der Programmierer, der den Code geschrieben hat, hat möglicherweise eine dieser beiden Anweisungen beabsichtigt:  
  
```  
a = i + (++j) a = (i++) + j  
```  
  
 Da der Parser das längstmögliche Token aus dem Eingabestream erstellt, wählt er die zweite Interpretation, die Token werden `i++`, `+` und `j`.  
  
## Siehe auch  
 [Lexikalische Konventionen](../cpp/lexical-conventions.md)