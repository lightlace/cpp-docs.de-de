---
title: "Verwenden von &quot;setjmp/longjmp&quot;"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "language-reference"
f1_keywords: 
  - "longjmp"
  - "setjmp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C++-Ausnahmebehandlung, setjmp/longjmp-Funktionen"
  - "longjmp-Funktion in C++-Programmen"
  - "setjmp-Funktion"
  - "setjmp-Funktion, C++-Programme"
  - "SETJMP.H"
  - "SETJMPEX.H"
ms.assetid: 96be8816-f6f4-4567-9a9c-0c3c720e37c5
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# Verwenden von &quot;setjmp/longjmp&quot;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wenn [setjmp](../c-runtime-library/reference/setjmp.md) und [longjmp](../c-runtime-library/reference/longjmp.md) zusammen verwendet werden, bieten sie die Möglichkeit, `goto` \(nicht lokal\) auszuführen.  Sie werden in der Regel verwendet, um die Ausführungssteuerung an den Fehlerbehandlungs\- oder Wiederherstellungscode in einer vorher aufgerufenen Routine zu übergeben, ohne die standardmäßigen Aufruf\- oder Rückgabekonventionen zu verwenden.  
  
> [!CAUTION]
>  `setjmp` und `longjmp` unterstützen jedoch die C\+\+\-Objektsemantik nicht und beeinträchtigen möglicherweise die Leistung, indem sie die Optimierung für lokale Variablen verhindern. Aus diesem Grund wird empfohlen, sie nicht in C\+\+\-Programmen zu verwenden.  Es wird empfohlen, stattdessen `try`\/`catch`\-Konstrukte zu verwenden.  
  
 Wenn Sie sich entscheiden, `setjmp`\/`longjmp` in einem C\+\+\-Programm zu verwenden, schließen Sie auch SETJMP.H oder SETJMPEX.H ein, um eine ordnungsgemäße Interaktion zwischen den Funktionen und der C\+\+\-Ausnahmebehandlung sicherzustellen.  Wenn Sie [\/EH](../build/reference/eh-exception-handling-model.md) für das Kompilieren verwenden, werden während der Stapelentladung Destruktoren für lokale Objekte aufgerufen.  Wenn Sie **\/EHs** zum Kompilieren verwenden und eine Ihrer Funktionen eine Funktion aufruft, die [nothrow](../cpp/nothrow-cpp.md) verwendet, und die Funktion, die `nothrow` verwendet, `longjmp` aufruft, dann findet, abhängig vom Optimierer, die Destruktorentladung möglicherweise nicht statt.  
  
 In portablem Code ist bei Ausführung eines nicht lokalen `goto`, das `longjmp` aufruft, die ordnungsgemäße Zerstörung von framebasierten Objekten möglicherweise unzuverlässig.  
  
## Siehe auch  
 [Kombination von C \(strukturiert\)\- und C\+\+\-Ausnahmen](../cpp/mixing-c-structured-and-cpp-exceptions.md)