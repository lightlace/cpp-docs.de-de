---
title: "Compilerfehler C2906"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "error-reference"
f1_keywords: 
  - "C2906"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2906"
ms.assetid: 30f652f1-6af6-4a2f-a69e-a1a4876cc8c6
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2906
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"Spezialisierung": Explizite Spezialisierung erfordert "Vorlage \<\>"  
  
 Für die explizite Spezialisierung von Vorlagen muss die neue Syntax verwendet werden.  
  
 Im folgenden Beispiel wird C2906 generiert:  
  
```  
// C2906.cpp  
// compile with: /c  
template<class T> class X{};   // primary template  
class X<int> { }   // C2906  
template<> class X<int> { };   // new syntax  
```