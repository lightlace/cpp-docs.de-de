---
title: "Compilerfehler C2646 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2646"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2646"
ms.assetid: 92ff1f02-5eaf-40a5-8b7a-a682f149e967
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# Compilerfehler C2646
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Eine anonyme Struktur oder Union im globalen Gültigkeitsbereich oder im Namespacebereich muss als statisch deklariert werden.  
  
 Eine anonyme Struktur oder Union verfügt über einen globalen Gültigkeitsbereich oder Namespacebereich, ist jedoch nicht als `static` deklariert.  
  
 Im folgenden Beispiel wird C2646 generiert und gezeigt, wie Sie diesen Fehler beheben:  
  
```  
// C2646.cpp  
// compile with: /c  
union { int i; };   // C2646 not static  
  
// OK  
static union { int j; };  
union U { int i; };  
```