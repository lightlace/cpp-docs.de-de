---
title: "Compilerfehler C3223"
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
  - "C3223"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3223"
ms.assetid: 1f4380b4-0413-40db-a868-62f97babaf78
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3223
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'eigenschaft': 'typeid' kann nicht auf eine Eigenschaft angewendet werden  
  
 Sie können [typeid](../../windows/typeid-cpp-component-extensions.md) nicht auf Eigenschaften anwenden.  
  
## Beispiel  
 Im folgenden Beispiel wird C3223 generiert:  
  
```  
// C3223.cpp // compile with: /clr ref class R { public: property int myprop; }; int main() { System::Type^ type2 = R::myprop::typeid;   // C3223 }  
```