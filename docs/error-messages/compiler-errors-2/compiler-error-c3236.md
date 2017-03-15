---
title: "Compilerfehler C3236 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3236"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3236"
ms.assetid: 4ef1871f-a348-44ae-922b-1e2081de20d0
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
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