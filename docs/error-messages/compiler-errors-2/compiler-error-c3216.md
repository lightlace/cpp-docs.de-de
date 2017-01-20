---
title: "Compilerfehler C3216"
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
  - "C3216"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3216"
ms.assetid: bbab1efe-8779-4489-8bb0-b11e45f5cbe5
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3216
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die Einschränkung muss ein generischer Parameter sein, nicht 'Typ'.  
  
 Eine Einschränkung wurde nicht ordnungsgemäß formatiert.  
  
 Im folgenden Beispiel wird C3216 generiert:  
  
```  
// C3216.cpp // compile with: /clr interface struct A {}; generic <class T> where F : A   // C3216 // Try the following line instead: // where T : A    // C3216 ref class C {};  
```  
  
 Das folgende Beispiel zeigt eine mögliche Lösung:  
  
```  
// C3216b.cpp // compile with: /clr /c interface struct A {}; generic <class T> where T : A ref class C {};  
```