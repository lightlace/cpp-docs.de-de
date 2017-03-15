---
title: "Compilerfehler C3464 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3464"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3464"
ms.assetid: 0ede05dc-4486-4921-8e8c-78ab5a2e09c5
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Compilerfehler C3464
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"Typ" Ein geschachtelter Typ kann nicht weitergeleitet werden.  
  
 Weiterleiten von Typen funktioniert nicht bei geschachtelten Typen.  
  
 Weitere Informationen finden Sie unter [Type Forwarding \(C\+\+\/CLI\)](../../windows/type-forwarding-cpp-cli.md).  
  
## Beispiel  
 Im folgenden Beispiel wird eine Komponente erstellt.  
  
```  
// C3464.cpp // compile with: /LD /clr public ref class R { public: ref class N {}; };  
```  
  
## Beispiel  
 Im folgenden Beispiel wird C3464 generiert:  
  
```  
// C3464_b.cpp // compile with: /clr /c #using "C3464.dll" [assembly:TypeForwardedTo(R::N::typeid)];   // C3464 [assembly:TypeForwardedTo(R::typeid)];   // OK  
```