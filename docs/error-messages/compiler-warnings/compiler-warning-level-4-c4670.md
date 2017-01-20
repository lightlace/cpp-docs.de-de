---
title: "Compilerwarnung (Stufe 4) C4670"
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
  - "C4670"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4670"
ms.assetid: e172b134-b1fb-4dfe-8e9d-209ea08b73c7
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung (Stufe 4) C4670
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'bezeichner': Auf diese Basisklasse kann nicht zugegriffen werden.  
  
 Auf die angegebene Klasse eines Objekts, das in einem **try**\-Block ausgelöst werden soll, kann nicht zugegriffen werden. Das Objekt kann nicht instanziiert werden, wenn es ausgelöst wird. Überprüfen Sie, ob die Basisklasse mit dem richtigen Zugriffsspezifizierer geerbt wird.  
  
 Im folgenden Beispiel wird C4670 generiert.  
  
```  
// C4670.cpp // compile with: /EHsc /W4 class A { }; class B : /* public */ A { } b;   // inherits A with private access by default int main() { try { throw b;   // C4670 } catch( B ) { } }  
```