---
title: "Compilerfehler C3291 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3291"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3291"
ms.assetid: ed2e9f89-8dbc-4387-bc26-cc955e840858
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# Compilerfehler C3291
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"default": Kann nicht der Name einer trivial\-Eigenschaft sein.  
  
 Eine trivial\-Eigenschaft kann nicht als `default` benannt werden. Weitere Informationen finden Sie unter [property](../../windows/property-cpp-component-extensions.md).  
  
## Beispiel  
 Im folgenden Beispiel wird C3291 generiert:  
  
```  
// C3291.cpp // compile with: /clr /c ref struct C { property System::String ^ default;   // C3291 property System::String ^ Default;   // OK };  
```