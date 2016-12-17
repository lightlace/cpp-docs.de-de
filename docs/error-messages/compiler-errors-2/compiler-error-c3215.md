---
title: "Compilerfehler C3215"
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
  - "C3215"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3215"
ms.assetid: d0d16007-8885-42e0-b086-2d3a61f348c5
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3215
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"Typ1": Der generische Typparameter wird bereits von "Typ2" eingeschränkt.  
  
 Eine Einschränkung wurde mehrmals angegeben.  
  
 Weitere Informationen zu Generika finden Sie unter [Generics](../../windows/generics-cpp-component-extensions.md).  
  
 Im folgenden Beispiel wird C3215 generiert:  
  
```  
// C3215.cpp // compile with: /clr interface struct A {}; generic <class T> where T : A,A ref class C {};   // C3215  
```  
  
 Mögliche Lösung:  
  
```  
// C3215b.cpp // compile with: /clr /c interface struct A {}; generic <class T> where T : A ref class C {};  
```