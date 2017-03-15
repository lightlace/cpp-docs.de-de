---
title: "Compilerwarnung (Stufe 3) C4636 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4636"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4636"
ms.assetid: 59112a0f-850f-41c6-bd84-8ae8dc84706a
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# Compilerwarnung (Stufe 3) C4636
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Auf 'construct' angewendeter XML\-Dokumentkommentar: Für das Tag ist ein nicht leeres Attribut erforderlich.  
  
 Ein Tag, wie etwa `cref`, wies keinen Wert auf.  
  
## Beispiel  
 Im folgenden Beispiel wird C4636 generiert:  
  
```  
// C4636.cpp // compile with: /clr /doc /W3 /c /// <see cref=''/> // /// <see cref='System::Exception'/> ref struct A {   // C4636 void f(int); }; // OK /// <see cref='System::Exception'/> ref struct B { void f(int); };  
```