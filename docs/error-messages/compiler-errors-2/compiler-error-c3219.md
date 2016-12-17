---
title: "Compilerfehler C3219"
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
  - "C3219"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3219"
ms.assetid: 9c9757b0-1256-4cdf-9d8c-a3a72f300ce5
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3219
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"param": Der generische Parameter kann nicht von mehreren Nichtschnittstellen eingeschränkt werden: "Klasse".  
  
 Es ist nicht zulässig, einen generischen Parameter durch zwei oder mehr verwaltete Klassen einzuschränken.  
  
 Im folgenden Beispiel wird C3219 generiert:  
  
```  
// C3219.cpp // compile with: /clr ref class A {}; ref class B {}; generic <class T> where T : A, B ref class E {};   // C3219  
```  
  
 Das folgende Beispiel zeigt eine mögliche Lösung:  
  
```  
// C3219b.cpp // compile with: /clr /c ref class A {}; interface struct C {}; generic <class T> where T : A ref class E {};  
```