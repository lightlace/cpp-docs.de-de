---
title: "Verwendung von strukturierter Ausnahmebehandlung in C++"
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
  - "C++-Ausnahmebehandlung, Kombiniert mit SEH"
  - "Strukturierte Ausnahmebehandlung, Mit C++-Ausnahmebehandlung"
ms.assetid: ec34b528-8c26-4429-b24a-6a68553aaa91
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Verwendung von strukturierter Ausnahmebehandlung in C++
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die in diesen Artikeln beschriebene strukturierte Ausnahmebehandlung funktioniert sowohl mit C\- als auch mit C\+\+\-Quelldateien.  Sie wurde jedoch nicht speziell für C\+\+ entwickelt und wird daher nicht empfohlen.  Sie können sicherstellen, dass der Code portabler ist, indem Sie die C\+\+\-Ausnahmebehandlung verwenden.  Der C\+\+\-Ausnahmebehandlungsmechanismus ist außerdem flexibler, da er Ausnahmen eines beliebigen Typs behandeln kann.  
  
 Microsoft C\+\+ unterstützt jetzt das C\+\+\-Ausnahmebehandlungsmodell auf Grundlage des ANSI C\+\+\-Standards.  Dieser Mechanismus behandelt automatisch die Zerstörung lokaler Objekte während der Stapelentladung.  Wenn Sie fehlertoleranten C\+\+\-Code schreiben und die Ausnahmebehandlung implementieren möchten, wird dringend empfohlen, die C\+\+\-Ausnahmebehandlung zu verwenden und nicht die strukturierte Ausnahmebehandlung. \(Beachten Sie Folgendes: Der C\+\+\-Compiler unterstützt Konstrukte für die strukturierte Ausnahmebehandlung, wie in diesen Artikeln beschrieben, der standardmäßige C\-Compiler unterstützt die C\+\+\-Ausnahmebehandlungssyntax jedoch nicht.\) Ausführliche Informationen über die C\+\+\-Ausnahmebehandlung finden Sie unter [C\+\+\-Ausnahmebehandlung](../cpp/cpp-exception-handling.md) und im *Annotated C\+\+ Reference Manual* von Ellis und Bjarne Margaret Stroustrup.  
  
## Siehe auch  
 [Strukturierte Ausnahmebehandlung](../cpp/structured-exception-handling-c-cpp.md)