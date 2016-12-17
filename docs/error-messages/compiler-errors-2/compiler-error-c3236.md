---
title: "Compilerfehler C3236"
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
  - "C3236"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3236"
ms.assetid: 4ef1871f-a348-44ae-922b-1e2081de20d0
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3236
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die explizite Instanziierung von Generika ist nicht zulässig.  
  
 Der Compiler lässt keine explizite Instanziierung von generischen Klassen zu.  
  
 Im folgenden Beispiel wird C3236 generiert:  
  
```  
// C3236.cpp // compile with: /clr generic<class T> public ref class X {}; generic ref class X<int>;   // C3236  
```  
  
 Das folgende Beispiel zeigt eine mögliche Lösung:  
  
```  
// C3236b.cpp // compile with: /clr /c generic<class T> public ref class X {};  
```