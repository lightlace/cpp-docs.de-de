---
title: "Compilerfehler C2995"
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
  - "C2995"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2995"
ms.assetid: a57cdfe0-b40b-4a67-a95c-1a49ace4842b
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2995
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

„function“: Funktionsvorlage wurde bereits definiert.  
  
 Stellen Sie sicher, dass nur eine Definition für jede Memberfunktion einer auf Vorlagen basierenden Klasse vorhanden ist.  
  
 Im folgenden Beispiel wird C2995 generiert:  
  
```  
// C2995.cpp // compile with: /c template <class T> void Test(T x){} template <class T> void Test(T x){}   // C2995 template <class T> void Test2(T x){}   // OK  
```