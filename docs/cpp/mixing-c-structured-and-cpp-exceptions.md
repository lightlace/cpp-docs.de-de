---
title: "Kombination von C (strukturiert)- und C++-Ausnahmen"
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
  - "C++-Ausnahmebehandlung, Gemischte Sprache"
  - "catch-Schlüsselwort [C++], Gemischt"
  - "Ausnahmen, Kombiniert (C und C++)"
  - "Strukturierte Ausnahmebehandlung, Kombiniert (C und C++)"
  - "try-catch-Schlüsselwort [C++], Gemischte Sprache"
ms.assetid: a149154e-36dd-4d1a-980b-efde2a563a56
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Kombination von C (strukturiert)- und C++-Ausnahmen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wenn Sie besser portierbaren Code schreiben möchten, wird das Verwenden der strukturierten Ausnahmebehandlung in einem C\+\+\-Programm nicht empfohlen.  Vielleicht möchten Sie jedoch gelegentlich mit **\/EHa** kompilieren und strukturierte Ausnahmen und C\+\+\-Quellcode kombinieren und benötigen daher einige Funktionen zur Behandlung beider Arten von Ausnahmen.  Da ein strukturierter Ausnahmehandler nicht über ein Konzept von Objekten oder von typisierten Ausnahmen verfügt, kann er keine Ausnahmen behandeln, die durch C\+\+\-Code ausgelöst werden. Allerdings können **catch**\-Handler von C\+\+ strukturierte Ausnahmen behandeln.  Deshalb wird die C\+\+\-Ausnahmebehandlungssyntax \(**try**, `throw`, **catch**\) nicht vom C\-Compiler akzeptiert, aber strukturierte Ausnahmebehandlungssyntax \(`__try`, `__except`, `__finally`\) wird vom C\+\+\-Compiler unterstützt.  
  
 Unter [\_set\_se\_translator](../c-runtime-library/reference/set-se-translator.md) finden Sie Informationen zur Behandlung strukturierter Ausnahmen als C\+\+\-Ausnahmen.  
  
 Wenn Sie strukturierte und C\+\+\-Ausnahmen kombinieren, beachten Sie Folgendes:  
  
1.  C\+\+\-Ausnahmen und strukturierte Ausnahmen können nicht in derselben Funktion kombiniert werden.  
  
2.  Beendigungshandler \(`__finally`\-Blöcke\) werden immer ausgeführt, sogar während des Entladens, nachdem eine Ausnahme ausgelöst wird.  
  
3.  Die C\+\+\-Ausnahmebehandlung kann Entladungssemantik in allen Modulen abfangen und beibehalten, die mit der Compileroption [\/EH](../build/reference/eh-exception-handling-model.md) kompiliert werden \(diese Option aktiviert die Entladungssemantik\).  
  
4.  Es kann Situationen geben, in denen Destruktorfunktionen nicht für alle Objekte aufgerufen werden.  Wenn beispielsweise eine strukturierte Ausnahme beim Versuch auftritt, einen Funktionsaufruf über einen nicht initialisierten Funktionszeiger auszuführen, und diese Funktion Objekte als Parameter nutzt, die vor dem Aufruf erstellt wurden, werden die Destruktoren dieser Objekte nicht während der Stapelentladung aufgerufen.  
  
## Worüber möchten Sie mehr erfahren?  
  
-   [Verwenden von setjmp oder longjmp in C\+\+\-Programmen](../cpp/using-setjmp-longjmp.md)  
  
-   [Unterschiede zwischen SEH und C\+\+ EH](../cpp/exception-handling-differences.md)  
  
## Siehe auch  
 [C\+\+\-Ausnahmebehandlung](../cpp/cpp-exception-handling.md)