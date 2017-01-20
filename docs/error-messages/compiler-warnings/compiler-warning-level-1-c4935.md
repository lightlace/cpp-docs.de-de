---
title: "Compilerwarnung (Stufe 1) C4935"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "C4935"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4935"
ms.assetid: a36c56d3-571a-44dd-bb0f-bcc6b020e134
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung (Stufe 1) C4935
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Assembly\-Zugriffsspezifizierer wurde von "Zugriff" geändert.  
  
 Die Sichtbarkeit einer Assembly eines Typs wurde geändert. Der Compiler verwendet den zuletzt gefundenen Spezifizierer. Die Sichtbarkeit einer Assembly einer Vorwärtsdeklaration kann sich z. B. von der Sichtbarkeit einer Assembly einer Klassendefinition unterscheiden.  
  
 C4935 ist nur über **\/clr:oldSyntax** erreichbar.  
  
 Im folgenden Beispiel wird C4935 generiert:  
  
```  
// C4935.cpp // compile with: /clr:oldSyntax /W1 /c public __gc public class X {   // C4935 int i; };  
```