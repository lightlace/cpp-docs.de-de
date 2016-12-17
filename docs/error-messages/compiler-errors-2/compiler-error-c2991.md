---
title: "Compilerfehler C2991"
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
  - "C2991"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2991"
ms.assetid: a87e4404-26e8-4927-b3ee-5d02b3b8bee1
caps.latest.revision: 11
caps.handback.revision: "11"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2991
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Neudefinition des Typparameters „parameter“  
  
 Es ist ein Typenkonflikt zwischen zwei generischen oder Vorlagendefinitionen von `parameter` aufgetreten. Wenn Sie mehrere generische oder Vorlagenparameter definieren, müssen Sie äquivalente Typen verwenden.  
  
 Im folgenden Beispiel wird C2991 generiert:  
  
```  
// C2991.cpp // compile with: /c template<class T, class T> struct TC {};   // C2991 // try the following line instead // template<class T, class T2> struct TC {};  
```  
  
 C2991 kann auch auftreten, wenn Generika verwendet werden:  
  
```  
// C2991b.cpp // compile with: /clr /c generic<class T,class T> ref struct GC {};   // C2991 // try the following line instead // generic<class T,class T2> ref struct GC {};  
```