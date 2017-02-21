---
title: "Compilerfehler C3865 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3865"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3865"
ms.assetid: 9bc62bb0-4fb8-4856-a5cf-c7cb4029a596
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Compilerfehler C3865
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Aufrufkonvention': Kann nur für systemeigene Memberfunktionen verwendet werden  
  
 Eine Aufrufkonvention wurde für eine Funktion verwendet, die entweder eine globale Funktion oder eine verwaltete Memberfunktion ist.  Die Aufrufkonvention kann nur für eine systemeigene \(nicht verwaltete\) Memberfunktion verwendet werden.  
  
 Weitere Informationen finden Sie unter [Aufrufkonventionen](../../cpp/calling-conventions.md).  
  
 Im folgenden Beispiel wird C3865 generiert:  
  
```  
// C3865.cpp  
// compile with: /clr  
// processor: x86  
void __thiscall Func(){}   // C3865  
  
// OK  
struct MyType {  
   void __thiscall Func(){}  
};  
```