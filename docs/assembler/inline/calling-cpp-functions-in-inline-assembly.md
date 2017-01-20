---
title: "Aufrufen von C++-Funktionen in der Inlineassembly"
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
helpviewer_keywords: 
  - "__asm-Schlüsselwort [C++], Aufrufende Funktionen"
  - "Funktionsaufrufe, C++-Funktionen"
  - "Funktionsaufrufe, In der Inlineassembly"
  - "Funktionen [C++], Aufrufen in der Inlineassembly"
  - "Inlineassembly, Aufrufende Funktionen"
  - "Visual C++, Funktionen"
ms.assetid: 1f0d1eb3-54cf-45d5-838d-958188616b38
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Aufrufen von C++-Funktionen in der Inlineassembly
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

## Microsoft\-spezifisch  
 Ein `__asm`\-Block kann nur globale C\+\+\-Funktionen aufrufen, die nicht überladen werden.  Wenn Sie eine überladene globale C\+\+\-Funktion oder Memberfunktion Ein C\+\+\-Compiler aufrufen, gibt der Compiler einen Fehler.  
  
 Sie können auch alle Funktionen aufzurufen deklariert mit **extern "C"**\-Bindung.  Dies stellt einen `__asm` Programms Block in C\-Format \+\+, um die C\-Bibliotheksfunktionen aufrufen, da alle standardmäßigen headerdateien die Bibliotheksfunktionen deklarieren, um **extern "C"**\-Bindung besitzt.  
  
 **BEENDEN Sie Microsoft\-Besonderen**  
  
## Siehe auch  
 [Inlineassembler](../../assembler/inline/inline-assembler.md)