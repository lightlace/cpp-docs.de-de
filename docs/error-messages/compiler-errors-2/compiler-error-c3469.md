---
title: "Compilerfehler C3469 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3469"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3469"
ms.assetid: e23b0e5c-c704-4e67-a868-bf02c2055d85
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Compilerfehler C3469
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'typ': Eine generische Klasse kann nicht weitergeleitet werden.  
  
 Typweiterleitung kann nicht für generische Klassen verwendet werden.  
  
 Weitere Informationen finden Sie unter [Type Forwarding \(C\+\+\/CLI\)](../../windows/type-forwarding-cpp-cli.md).  
  
## Beispiel  
 Im folgenden Beispiel wird eine Komponente erstellt:  
  
```  
// C3469.cpp // compile with: /clr /LD generic<typename T> public ref class GR {}; public ref class GR2 {};  
```  
  
## Beispiel  
 Im folgenden Beispiel wird C3466 generiert:  
  
```  
// C3469_b.cpp // compile with: /clr /c #using "C3469.dll" [assembly:TypeForwardedTo(GR::typeid)];   // C3469 [assembly:TypeForwardedTo(GR2::typeid)];   // OK  
```