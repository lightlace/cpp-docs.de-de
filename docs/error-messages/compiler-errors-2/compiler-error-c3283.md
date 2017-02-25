---
title: "Compilerfehler C3283 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3283"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3283"
ms.assetid: c51d912c-cde3-4928-904e-26734c8954ce
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Compilerfehler C3283
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"Typ": Eine Schnittstelle darf keinen Instanzenkonstruktor aufweisen  
  
 Eine CLR\-[Schnittstelle](../../windows/interface-class-cpp-component-extensions.md) darf keinen Instanzenkonstruktor aufweisen.  Ein statischer Konstruktor ist zulässig.  
  
 Im folgenden Beispiel wird C3283 generiert:  
  
```  
// C3283.cpp // compile with: /clr interface class I { I();   // C3283 };  
```  
  
 Mögliche Lösung:  
  
```  
// C3283b.cpp // compile with: /clr /c interface class I { static I(){} };  
```