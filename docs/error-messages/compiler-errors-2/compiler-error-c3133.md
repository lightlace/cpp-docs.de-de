---
title: "Compilerfehler C3133 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3133"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3133"
ms.assetid: 4a709405-b67b-4061-8a2a-19fa5fb34a2a
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Compilerfehler C3133
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Attribute können nicht auf C\+\+\-Variablenargumente angewendet werden.  
  
 Ein Attribut wurde falsch angewendet.  Attribute können nicht auf ein Auslassungszeichen angewendet werden, das variable Argumente darstellt.  
  
 Weitere Informationen finden Sie unter [User\-Defined Attributes](../../windows/user-defined-attributes-cpp-component-extensions.md).  
  
## Beispiel  
 Im folgenden Beispiel wird C3133 generiert.  
  
```  
// C3133.cpp  
// compile with: /clr /c  
ref struct MyAttr: System::Attribute {};   
void Func([MyAttr]...);   // C3133  
void Func2([MyAttr] int i);   // OK  
```