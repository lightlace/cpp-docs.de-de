---
title: "Compilerwarnung C4693"
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
  - "C4693"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4693"
ms.assetid: 72d8db01-5e6f-4794-8731-76107e8f064a
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung C4693
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"class": Eine versiegelte abstrakte Klasse kann keine Test\-Instanzmember aufweisen  
  
 Wenn ein Typ als [sealed](../../windows/sealed-cpp-component-extensions.md) und [abstract](../../windows/abstract-cpp-component-extensions.md) gekennzeichnet ist, kann er nur statische Member aufweisen.  
  
## Beispiel  
 Im folgenden Beispiel wird C4693 generiert:  
  
```  
// C4693.cpp // compile with: /clr /c public ref class Public_Ref_Class sealed abstract { public: void Test() {}   // C4693 static void Test2() {}   // OK };  
```