---
title: "Quelldateien und Quellprogramme | Microsoft Docs"
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
  - "Dateien [C++], Quelle"
  - "Programme [C++], Quelle"
  - "Quelldateien, Angeben im Compiler"
  - "Quellprogramme"
ms.assetid: 18bb2826-17da-48e5-92a2-10e649f1bc9f
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# Quelldateien und Quellprogramme
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ein Quellprogramm kann in eine oder mehrere "Quelldateien" oder in "Übersetzungseinheiten" aufgeteilt werden. Die Eingabe in den Compiler wird als "Übersetzungseinheit" bezeichnet.  
  
## Syntax  
 *translation\-unit*:  
 *external\-declaration*  
  
 *translation\-unit external\-declaration*  
  
 *external\-declaration*:  
 *function\-definition*  
  
 *declaration*  
  
 [Übersicht über Deklarationen](../c-language/overview-of-declarations.md) gibt die Syntax für das `declaration`\-Nichtterminal an, und in der *Präprozessorreferenz* wird erläutert, wie die [Übersetzungseinheit](../preprocessor/phases-of-translation.md) verarbeitet wird.  
  
> [!NOTE]
>  Eine Erläuterung der ANSI\-Syntaxkonventionen erhalten Sie in der Einführung zur [Zusammenfassung der C\-Sprachsyntax](../c-language/c-language-syntax-summary.md).  
  
 Die Komponenten einer Übersetzungseinheit sind externe Deklarationen, die Funktionsdefinitionen und Bezeichnerdeklarationen enthalten.  Diese Deklarationen und Definitionen können sich in den Quelldateien, Headerdateien, Bibliotheken und anderen Dateien befinden, die das Programm benötigt.  Sie müssen jede Übersetzungseinheit kompilieren und die resultierenden Objektdateien verknüpfen, um ein Programm zu erstellen.  
  
 Ein Quellprogramm ist bei C eine Auflistung von Direktiven, Pragmas, Deklarationen, Definitionen, Anweisungsblöcken und Funktionen.  Um als gültige Komponenten eines Microsoft\-C\-Programms zu gelten, muss jede Komponente die Syntax aufweisen, die in diesem Buch beschrieben wird. Die Komponenten können jedoch \(gemäß den Regeln in diesem Buch\) in beliebiger Reihenfolge im Programm angezeigt werden.  Allerdings wirkt sich der Speicherort dieser Komponenten in einem Programm darauf aus, wie Variablen und Funktionen in einem Programm verwendet werden können. \(Weitere Informationen erhalten Sie unter [Lebensdauer, Bereich, Sichtbarkeit und Verknüpfung](../c-language/lifetime-scope-visibility-and-linkage.md).\)  
  
 Quelldateien müssen keine ausführbaren Anweisungen enthalten.  Beispielsweise finden Sie es vielleicht hilfreich, Definitionen von Variablen in einer Quelldatei einzufügen und dann Verweise auf diese Variablen in anderen Quelldateien, die diese verwenden, zu deklarieren.  Diese Vorgehensweise erleichtert das Suchen und ggf. Aktualisieren der Definitionen.  Aus demselben Grund werden Konstanten und Makros häufig in separaten Dateien strukturiert, die "Includedateien" oder "Headerdateien" genannt werden und auf die nach Bedarf in Quelldateien verwiesen werden kann.  Weitere Informationen zu [Makros](../preprocessor/macros-c-cpp.md) und [Includedateien](../preprocessor/hash-include-directive-c-cpp.md) finden Sie in der *Präprozessorreferenz*.  
  
## Siehe auch  
 [Programmstruktur](../c-language/program-structure.md)