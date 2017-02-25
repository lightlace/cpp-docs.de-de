---
title: "Compilerfehler C2756 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2756"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2756"
ms.assetid: 42eb988d-4043-4dee-8fd4-596949f69a55
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Compilerfehler C2756
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'template type': Bei einer teilweisen Spezialisierung sind Standardvorlagenargumente nicht zulässig  
  
 Die Vorlage für eine teilweise Spezialisierung darf kein Standardargument enthalten.  
  
 Im folgenden Beispiel wird C2756 generiert und gezeigt, wie Sie diesen Fehler beheben:  
  
```  
// C2756.cpp  
template <class T>  
struct S {};  
  
template <class T=int>  
// try the following line instead  
// template <class T>  
struct S<T*> {};   // C2756  
```