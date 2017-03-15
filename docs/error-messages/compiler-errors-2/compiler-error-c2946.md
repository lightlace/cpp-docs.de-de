---
title: "Compilerfehler C2946 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C2946"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2946"
ms.assetid: c86dfbfc-7702-4f09-8a53-d205710e99c2
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Compilerfehler C2946
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Explizite Instanziierung: "Klasse" ist keine Spezialisierung einer Vorlagenklasse  
  
 Nicht auf Vorlagen basierende Klassen können nicht explizit instanziiert werden.  
  
## Beispiel  
 Im folgenden Beispiel wird C2946 generiert.  
  
```  
// C2946.cpp class C {}; template C;  // C2946 int main() {}  
```