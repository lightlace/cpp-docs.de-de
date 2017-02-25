---
title: "Compilerwarnung (Stufe 4) C4189 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4189"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4189"
ms.assetid: 7ad9242c-228e-4054-8244-5e914b618ef3
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Compilerwarnung (Stufe 4) C4189
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"Bezeichner": Lokale Variable ist initialisiert, aber nicht referenziert  
  
 Eine Variable wird deklariert und initialisiert, aber nicht verwendet.  
  
 Im folgenden Beispiel wird C4189 generiert.  
  
```  
// C4189.cpp // compile with: /W4 int main() { int a = 1;   // C4189, remove declaration to resolve }  
```