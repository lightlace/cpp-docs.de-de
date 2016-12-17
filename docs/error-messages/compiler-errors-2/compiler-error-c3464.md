---
title: "Compilerfehler C3464"
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
  - "C3464"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3464"
ms.assetid: 0ede05dc-4486-4921-8e8c-78ab5a2e09c5
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
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