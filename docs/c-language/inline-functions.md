---
title: "Inlinefunktionen"
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
  - "Schneller Code"
  - "Funktionen [C++], Inlinefunktionen"
  - "Inlinefunktionen, __inline-Schlüsselwort"
ms.assetid: 00f4b2ff-8ad0-4165-9f4c-2ef157d03f31
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "mblome"
manager: "ghogen"
---
# Inlinefunktionen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Das `__inline`\-Schlüsselwort weist den Compiler an, den Code in der Funktionsdefinition für jede Instanz eines Funktionsaufrufs zu ersetzen.  Die Ersetzung wird allerdings nur nach Ermessen des Compilers ausgeführt.  Zum Beispiel führt der Compiler eine Funktion nicht inline aus, wenn ihre Adresse akzeptiert wird oder wenn sie für den Inlinevorgang zu groß ist.  
  
 Damit eine Funktion als Kandidat für das Inlining in Betracht gezogen werden kann, muss sie die neue Funktionsdefinition verwenden.  
  
 Verwenden Sie dieses Format, um eine Inlinefunktion anzugeben:  
  
 `__inline` *type*opt *function\-definition*`;`  
  
 Die Verwendung von Inlinefunktionen generiert einen schnelleren Code und kann manchmal auch kleineren Code generierten als der entsprechende Funktionsaufruf. Das hat folgende Gründe:  
  
-   Die Zeit, die erforderlich ist, um Funktionsaufrufe ausführen, wird gespart.  
  
-   Kleine Inlinefunktionen, etwa drei Zeilen oder weniger, erstellen weniger Code als der entsprechende Funktionsaufruf, da der Compiler keinen Code generiert, um Argumente und einen Rückgabewert zu behandeln.  
  
-   Inline generierte Funktionen werden Codeoptimierungen unterzogen, die für normale Funktionen nicht verfügbar sind, da der Compiler keine interprozeduralen Optimierungen durchführt.  
  
 Funktionen, die `__inline` verwenden, sollten nicht mit Inlineassemblercode verwechselt werden.  Weitere Informationen erhalten Sie unter [Inlineassembler](../c-language/inline-assembler-c.md).  
  
 **END Microsoft\-spezifisch**  
  
## Siehe auch  
 [inline, \_\_inline, \_\_forceinline](../misc/inline-inline-forceinline.md)