---
title: "Compilerfehler C3299 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3299"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3299"
ms.assetid: 7cabdf01-bceb-404f-9401-cdd9c7fc1641
caps.latest.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 4
---
# Compilerfehler C3299
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"Member\_Funktion": Einschränkungen können nicht angegeben werden, sie werden von der Basismethode geerbt.  
  
 Wenn Sie eine generische Memberfunktion überschreiben, können Sie keine Einschränkungsklauseln angeben \(das Wiederholen von Einschränkungen impliziert, dass die Einschränkungen nicht geerbt werden\).  
  
 Die Einschränkungsklauseln für die generische Funktion, die Sie überschreiben, werden geerbt.  
  
 Weitere Informationen finden Sie unter [Constraints on Generic Type Parameters \(C\+\+\/CLI\)](../../windows/constraints-on-generic-type-parameters-cpp-cli.md).  
  
## Beispiel  
 Im folgenden Beispiel wird C3299 generiert:  
  
```  
// C3299.cpp // compile with: /clr /c public ref struct R { generic<class T> where T : R virtual void f(); }; public ref struct S : R { generic<class T> where T : R   // C3299 virtual void f() override; };  
```