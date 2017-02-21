---
title: "Compilerwarnung (Stufe 4) C4985 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4985"
ms.assetid: 832f001c-afe7-403d-a8b4-02334724c79e
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Compilerwarnung (Stufe 4) C4985
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"Symbolname": Attribute sind in vorheriger Deklaration nicht vorhanden.  
  
 Die Microsoft SAL\-Anmerkungen \(Source Code Annotation Language, Quellcodeanmerkungssprache\) zur aktuellen Methodendeklaration oder \-definition unterscheiden sich von den Anmerkungen zu einer früheren Deklaration. In der Definition und den Deklarationen einer Methode müssen dieselben SAL\-Anmerkungen verwendet werden.  
  
 Die SAL stellt einen Satz Anmerkungen bereit, mit denen Sie beschreiben können, wie eine Funktion ihre Parameter verwendet, welche Annahmen sie über diese Parameter trifft, und wie ihr garantierte Ergebnis aussieht, wenn sie abgeschlossen wird. Die Anmerkungen sind in der Headerdatei „sal.h“ definiert.  
  
 Beachten Sie, dass die SAL\-Makros nicht erweitert werden, es sei denn, für das Projekt ist das Kennzeichen [\/ analyze](../../build/reference/analyze-code-analysis.md) angegeben. Wenn Sie **\/analyze** angeben, kann der Compiler C4985 auslösen, selbst wenn ohne **\/analyze** keine Warnungen oder Fehler angezeigt würden.  
  
### So beheben Sie diesen Fehler  
  
1.  Verwenden Sie für die Definition einer Methode und deren Deklarationen dieselben SAL\-Anmerkungen.  
  
## Siehe auch  
 [SAL\-Anmerkungen](../../c-runtime-library/sal-annotations.md)