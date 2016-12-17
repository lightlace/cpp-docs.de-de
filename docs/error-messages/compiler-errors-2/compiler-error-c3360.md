---
title: "Compilerfehler C3360"
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
  - "C3360"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3360"
ms.assetid: 6acf983a-dbb6-422b-b045-a34bb4ba6761
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3360
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"Zeichenfolge": Name kann nicht erstellt werden.  
  
 Der Wert, der an das [uuid](../../windows/uuid-cpp-attributes.md)\-Attribut übergeben wurde, war ungültig.  
  
 Im folgenden Beispiel wird C3360 generiert:  
  
```  
// C3360.cpp [ uuid("1") ] // try this line instead // [ uuid("12341234-1234-1234-1234-123412341234") ] struct A   // C3360 { }; int main() { }  
```