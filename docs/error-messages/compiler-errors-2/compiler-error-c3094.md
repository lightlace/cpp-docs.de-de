---
title: "Compilerfehler C3094 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3094"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3094"
ms.assetid: 10da9b7c-e72d-4013-9925-c83e1bb142db
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Compilerfehler C3094
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"Attribut": Eine anonyme Verwendung ist nicht zulässig.  
  
 Ein Attribut wurde nicht ordnungsgemäß festgelegt.  Weitere Informationen finden Sie unter [User\-Defined Attributes](../../windows/user-defined-attributes-cpp-component-extensions.md).  
  
## Beispiel  
 Im folgenden Beispiel wird C3094 generiert.  
  
```  
// C3094.cpp // compile with: /clr /c using namespace System; [AttributeUsage(AttributeTargets::Class)] public ref class AAttribute : Attribute {}; [A];   // C3094 // OK [A] ref class x{};  
```