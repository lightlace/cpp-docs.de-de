---
title: "Compilerfehler C3468 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3468"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3468"
ms.assetid: cfd320db-2f6e-4e0d-ba02-e79ece87e1e0
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Compilerfehler C3468
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"Typ": Sie können einen Typ nur an eine Assembly weiterleiten:  
  
 `file` ist keine Assembly.  
  
 Es können nur Typen in einer Assembly weitergeleitet werden.  
  
 Weitere Informationen finden Sie unter [Type Forwarding \(C\+\+\/CLI\)](../../windows/type-forwarding-cpp-cli.md).  
  
## Beispiel  
 Im folgenden Beispiel wird ein Modul erstellt.  
  
```  
// C3468.cpp // compile with: /LN /clr public ref class R {};  
```  
  
## Beispiel  
 Im folgenden Beispiel wird C3468 generiert:  
  
```  
// C3468_b.cpp // compile with: /clr /c #using "C3468.netmodule" [ assembly:TypeForwardedTo(R::typeid) ];   // C3468  
```