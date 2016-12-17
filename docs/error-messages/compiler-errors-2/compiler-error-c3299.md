---
title: "Compilerfehler C3299"
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
  - "C3299"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3299"
ms.assetid: 7cabdf01-bceb-404f-9401-cdd9c7fc1641
caps.latest.revision: 4
caps.handback.revision: "4"
ms.author: "corob"
manager: "ghogen"
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