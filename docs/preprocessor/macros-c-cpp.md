---
title: "Makros (C/C++)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "Präprozessor"
  - "Präprozessor, Makros"
  - "Visual C++, Präprozessormakros"
ms.assetid: a7bfc5d4-2537-4fe0-bef0-70cec0b43388
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Makros (C/C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Vorverarbeitung erweitert Makros in allen Zeilen, die keine Präprozessordirektiven sind \(Zeilen, die kein **\#** als erstes Nichtleerzeichen aufweisen\), und in Teilen einiger Direktiven, die nicht als Teil einer bedingten Kompilierung übersprungen werden. "Direktiven für die bedingte Kompilierung" ermöglichen es Ihnen, die Kompilierung von Teilen einer Quelldatei zu unterdrücken, indem sie einen konstanten Ausdruck oder einen Bezeichner testen, um zu bestimmen, welche Textblöcke an den Compiler übergeben werden und welche Textblöcke während des Präprozessorlaufs aus der Quelldatei entfernt werden .  
  
 Die `#define`\-Direktive wird normalerweise verwendet, um aussagekräftige Bezeichner Konstanten, Schlüsselwörtern und häufig verwendeten Anweisungen oder Ausdrücken zuzuordnen.  Bezeichner, die Konstanten darstellen, werden manchmal als "symbolische Konstanten "oder" Manifestkonstanten" bezeichnet. Bezeichner, die Anweisungen oder Ausdrücke darstellen, werden als "Makros" bezeichnet. In dieser Präprozessordokumentation wird nur der Begriff "Makro" verwendet.  
  
 Wenn der Name des Makros im Programmquelltext oder in den Argumenten von bestimmten anderen Präprozessorbefehlen erkannt wird, wird er als Aufruf dieses Makros behandelt.  Der Makroname wird durch eine Kopie des Makrotexts ersetzt.  Wenn das Makro Argumente akzeptiert, werden die tatsächlichen Argumente nach dem Makronamen durch formale Parameter im Makrotext ersetzt.  Der Prozess des Ersetzens eines Makroaufrufs durch die verarbeitete Textkopie wird als "Erweiterung" des Makroaufrufs bezeichnet.  
  
 Praktisch gibt es zwei Arten von Makros. "Object\-like"\-Makros akzeptieren keine Argumente, während "function\-like"\-Makros definiert werden können, um Argumente zu akzeptieren, damit sie wie Funktionsaufrufe aussehen und wie solche reagieren.  Da Makros keine tatsächlichen Funktionsaufrufe generieren, können Sie manchmal erreichen, dass Programme schneller ausgeführt werden, indem Sie Funktionsaufrufe durch Makros ersetzen. \(In C\+\+ sind Inlinefunktionen häufig eine bevorzugte Methode.\) Makros können jedoch Probleme verursachen, wenn Sie sie nicht sorgfältig definieren und verwenden.  Möglicherweise müssen Sie Klammern bei Makrodefinitionen mit Argumenten verwenden, um die gewünschte Rangfolge in einem Ausdruck zu erhalten.  Makros behandeln außerdem Ausdrücke mit Nebeneffekte möglicherweise nicht ordnungsgemäß.  Weitere Informationen finden Sie im `getrandom`\-Beispiel in der [\#define\-Direktive](../preprocessor/hash-define-directive-c-cpp.md).  
  
 Sobald Sie ein Makro definiert haben, können Sie es nicht mit einem anderen Wert neu definieren, ohne zuerst die ursprüngliche Definition zu entfernen.  Sie können jedoch das Makro mit genau derselben Definition neu definieren.  Daher kann dieselbe Definition in einem Programm mehrmals vorkommen.  
  
 Die \#**undef**\-Direktive entfernt die Definition eines Makros.  Sobald Sie die Definition entfernt haben, können Sie das Makro mit einem anderen Wert neu definieren.  Unter [\#define\-Direktive](../preprocessor/hash-define-directive-c-cpp.md) und  [\#undef\-Direktive](../preprocessor/hash-undef-directive-c-cpp.md) werden die `#define`\- und `#undef`\-Direktiven erläutert.  
  
 Weitere Informationen finden Sie unter  
  
-   [Makros und C\+\+](../preprocessor/macros-and-cpp.md)  
  
-   [Variadic\-Makros](../preprocessor/variadic-macros.md)  
  
-   [Vordefinierte Makros](../preprocessor/predefined-macros.md)  
  
## Siehe auch  
 [C\/C\+\+\-Präprozessorreferenz](../preprocessor/c-cpp-preprocessor-reference.md)