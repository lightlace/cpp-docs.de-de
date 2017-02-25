---
title: "Compilerfehler C3075 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3075"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3075"
ms.assetid: f431daa9-e0fa-48f0-a5c3-f99be96b55e3
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# Compilerfehler C3075
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Instanz': Eine Instanz eines Verweistyps 'Typ' kann nicht in einen Werttyp eingebettet werden.  
  
 Ein Werttyp kann keine Instanz eines Verweistyps enthalten.  
  
 Weitere Informationen finden Sie unter [C\+\+\-Stack\-Semantik für Referenztypen](../../dotnet/cpp-stack-semantics-for-reference-types.md).  
  
## Beispiel  
 Im folgenden Beispiel wird C3075 generiert:  
  
```  
// C3075.cpp // compile with: /clr /c ref struct U {}; value struct X { U y;   // C3075 }; ref struct Y { U y;   // OK };  
```