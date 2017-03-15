---
title: "Compilerwarnung (Stufe 1) C4813 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4813"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4813"
ms.assetid: c30bf877-ab04-4fe4-897e-8162092426f0
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Compilerwarnung (Stufe 1) C4813
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Funktion': Eine Friend\-Funktion einer lokalen Klasse muss bereits deklariert sein.  
  
 Eine Friend\-Funktion in einer inneren Klasse wurde in der äußeren Klasse nicht deklariert.  
  
 Im folgenden Beispiel wird C4813 generiert:  
  
```  
// C4813.cpp // compile with: /W1 /LD void MyClass() { // void func(); class InnerClass { friend void func();   // C4813 uncomment declaration above }; }  
```