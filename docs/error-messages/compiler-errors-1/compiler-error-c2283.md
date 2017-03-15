---
title: "Compilerfehler C2283 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C2283"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2283"
ms.assetid: 8a5b3175-b480-4598-a1f7-0b50504c5caa
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Compilerfehler C2283
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"Bezeichner": Ein reiner Spezifizierer oder ein abstrakter Überschreibungsspezifizierer ist für "Struktur" \(unbenannt\) nicht zulässig.  
  
 Eine Memberfunktion einer unbenannten Klasse oder Struktur wird mit einem reinen Spezifizierer deklariert, was nicht zulässig ist.  
  
 Im folgenden Beispiel wird C2283 generiert:  
  
```  
// C2283.cpp // compile with: /c struct { virtual void func() = 0;   // C2283 }; struct T { virtual void func() = 0;   // OK };  
```