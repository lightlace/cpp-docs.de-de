---
title: "Compilerwarnung (Stufe 2) C4396 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4396"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4396"
ms.assetid: 7cd6b283-db17-4574-b299-03e0b913ad70
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# Compilerwarnung (Stufe 2) C4396
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"Name": Der Inlinespezifizierer kann nicht verwendet werden, wenn eine Friend\-Deklaration auf die Spezialisierung einer Funktionsvorlage verweist.  
  
 Für die Spezialisierung einer Funktionsvorlage kann kein [Inline](../../misc/inline-inline-forceinline.md)\-Spezifizierer angegeben werden. Der Compiler gibt die Warnung C4396 aus und ignoriert den Inlinespezifizierer.  
  
### So beheben Sie diesen Fehler  
  
-   Entfernen Sie den `inline`\-, `__inline`\- oder `__forceinline`\-Spezifizierer aus der Deklaration der Friend\-Funktion.  
  
## Beispiel  
 Das folgende Codebeispiel enthält eine ungültige Friend\-Funktionsdeklaration mit einem `inline`\-Spezifizierer.  
  
```  
// C4396.cpp // compile with: /W2 /c class X; template<class T> void Func(T t, int i); class X { friend inline void Func<char>(char t, int i);  //C4396 // try the following line instead //    friend void Func<char>(char t, int i); int i; };  
```