---
title: "Compilerfehler C2995 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C2995"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2995"
ms.assetid: a57cdfe0-b40b-4a67-a95c-1a49ace4842b
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Compilerfehler C2995
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

„function“: Funktionsvorlage wurde bereits definiert.  
  
 Stellen Sie sicher, dass nur eine Definition für jede Memberfunktion einer auf Vorlagen basierenden Klasse vorhanden ist.  
  
 Im folgenden Beispiel wird C2995 generiert:  
  
```  
// C2995.cpp // compile with: /c template <class T> void Test(T x){} template <class T> void Test(T x){}   // C2995 template <class T> void Test2(T x){}   // OK  
```