---
title: "Pr&#228;prozessordirektiven"
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
  - "Direktiven, Präprozessor"
  - "Präprozessor, Direktiven"
ms.assetid: e0fc4564-b6cf-4a36-bf51-6ccd7abd0a94
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Pr&#228;prozessordirektiven
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Präprozessordirektiven wie `#define` und **\#ifdef** werden in der Regel verwendet, um das Ändern und Kompilieren von Quellprogrammen in verschiedenen Ausführungsumgebungen zu vereinfachen.  Direktiven in der Quelldatei weisen den Präprozessor an, bestimmte Aktionen auszuführen.  Beispielsweise kann der Präprozessor Token im Text ersetzen, den Inhalt von anderen Dateien in die Quelldatei einfügen oder die Kompilierung eines Teils der Datei unterdrücken, indem er Textabschnitte entfernt.  Präprozessorzeilen werden vor der Makroerweiterung erkannt und ausgeführt.  Wenn also die Erweiterung eines Makros aussieht wie ein Präprozessorbefehl, wird dieser Befehl nicht vom Präprozessor erkannt.  
  
 Präprozessoranweisungen verwenden den gleichen Zeichensatz wie Quelldateianweisungen, mit der Ausnahme, dass Escapesequenzen nicht unterstützt werden.  Der Zeichensatz, der in Präprozessoranweisungen verwendet wird, ist mit dem [Ausführungszeichensatz](assetId:///a7901c61-524d-47c6-beb6-d9dacc2e72ed) identisch.  Der Präprozessor erkennt auch negative Zeichenwerte.  
  
 Der Präprozessor erkennt die folgenden Direktiven:  
  
|||||  
|-|-|-|-|  
|[\#define](../preprocessor/hash-define-directive-c-cpp.md)|[\#error](../preprocessor/hash-error-directive-c-cpp.md)|[\#import](../preprocessor/hash-import-directive-cpp.md)|[\#undef](../preprocessor/hash-undef-directive-c-cpp.md)|  
|[\#elif](../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md)|[\#if](../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md)|[\#include](../preprocessor/hash-include-directive-c-cpp.md)|[\#using](../preprocessor/hash-using-directive-cpp.md)|  
|[\#else](../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md)|[\#ifdef](../preprocessor/hash-ifdef-and-hash-ifndef-directives-c-cpp.md)|[\#line](../preprocessor/hash-line-directive-c-cpp.md)|[\#endif](../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md)|  
|[\#ifndef](../preprocessor/hash-ifdef-and-hash-ifndef-directives-c-cpp.md)|[\#pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)|||  
  
 Das Nummernzeichen \(**\#**\) muss das erste Zeichen ohne Leerstelle in der Zeile sein, die die Direktive enthält. Leerzeichen können zwischen dem Nummernzeichen und dem ersten Buchstaben der Direktive gesetzt werden.  Manche Direktiven enthalten Argumente oder Werte.  Jeglichem Text, der auf eine Direktive folgt \(außer einem Argument oder einem Wert, der Teil der Direktive ist\), muss das einzeilige Kommentartrennzeichen \(**\/\/**\) vorangestellt sein, oder er muss in Kommentartrennzeichen \(**\/\* \*\/**\) eingeschlossen werden.  Zeilen, die Präprozessordirektiven enthalten, können fortgesetzt werden, indem direkt vor den Zeilenendemarker ein umgekehrter Schrägstrich \(**\\**\) gesetzt wird.  
  
 Präprozessordirektiven können an beliebiger Stelle in einer Quelldatei auftreten, aber sie gelten nur für den Rest der Quelldatei.  
  
## Siehe auch  
 [Präprozessoroperatoren](../preprocessor/preprocessor-operators.md)   
 [Vordefinierte Makros](../preprocessor/predefined-macros.md)   
 [C\/C\+\+\-Präprozessorreferenz](../preprocessor/c-cpp-preprocessor-reference.md)