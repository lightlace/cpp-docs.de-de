---
title: "Compilerfehler C2929 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C2929"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2929"
ms.assetid: 11134027-6adc-4733-b6bd-b94486bd1933
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Compilerfehler C2929
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"Bezeichner": Explizite Instanziierung; Instanziierung eines Elements einer Vorlagenklasse kann nicht explizit erzwungen und unterdrückt werden  
  
 Sie können einen Bezeichner nicht explizit instanziieren und gleichzeitig verhindern, dass er instanziiert wird.  
  
 Im folgenden Beispiel wird C2929 generiert:  
  
```  
// C2929.cpp // compile with: /c template<typename T> class A { public: A() {} }; template A<int>::A(); extern template A<int>::A();   // C2929  
```