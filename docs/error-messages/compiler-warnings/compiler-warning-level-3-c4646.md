---
title: "Compilerwarnung (Stufe 3) C4646"
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
  - "C4646"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4646"
ms.assetid: 23677e8e-603e-40e0-b99a-2e4894a1278e
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung (Stufe 3) C4646
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Eine Funktion, die mit "\_\_declspec\(noreturn\)" deklariert wurde, hat einen nicht leeren Rückgabetyp  
  
 Eine mit dem [noreturn](../../cpp/noreturn.md) `__declspec`\-Modifizierer gekennzeichnete Funktion muss den [void](../../cpp/void-cpp.md)\-Rückgabetyp aufweisen.  
  
 Im folgenden Beispiel wird C4646 generiert:  
  
```  
// C4646.cpp // compile with: /W3 /WX int __declspec(noreturn) TestFunction() {   // C4646  make return type void }  
```