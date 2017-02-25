---
title: "Compilerfehler C3226 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3226"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3226"
ms.assetid: 636106ca-6f4e-4303-a6a0-8803221ec67d
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# Compilerfehler C3226
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Innerhalb einer generischen Deklaration ist keine Vorlagendeklaration zulässig.  
  
 Verwenden Sie eine generische Deklaration innerhalb einer generischen Klasse.  
  
 Im folgenden Beispiel wird C3226 generiert:  
  
```  
// C3226.cpp // compile with: /clr generic <class T> ref class C { template <class T1>   // C3226 ref struct S1 {}; };  
```  
  
 Das folgende Beispiel zeigt eine mögliche Lösung:  
  
```  
// C3226b.cpp // compile with: /clr /c generic <class T> ref class C { generic <class T1> ref struct S1 {}; };  
```