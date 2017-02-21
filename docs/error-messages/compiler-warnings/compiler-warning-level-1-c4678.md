---
title: "Compilerwarnung (Stufe 1) C4678 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4678"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4678"
ms.assetid: 0c588f34-595d-4e5c-9470-8723fca2cc06
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# Compilerwarnung (Stufe 1) C4678
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Basisklasse "base\_type" hat eine stärkere Zugriffsbeschränkung als "derived\_type"  
  
 Ein öffentlicher Typ wurde von einem privaten Typ abgeleitet. Wenn der öffentliche Typ in einer referenzierten Assembly instanziiert wird, sind die Member des privaten Basistyps nicht zugänglich.  
  
 C4678 ist nur mit **\/clr:oldSyntax** erreichbar. Bei Verwendung von **\/clr** stellt eine stärkere Beschränkung auf der Basisklasse im Vergleich zur abgeleiteten Klasse einen Fehler dar.  
  
 Im folgenden Beispiel wird C4678 generiert:  
  
```  
// C4678.cpp // compile with: /clr:oldSyntax /LD /W1 #using <mscorlib.dll> private __gc struct privateG { // try the following line instead // public __gc struct privateG { public: int i; }; public __gc struct V: public privateG {   // C4678 public: int j; };  
```