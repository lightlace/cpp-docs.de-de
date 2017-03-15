---
title: "Compilerfehler C2326 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C2326"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2326"
ms.assetid: 01a5ea40-de83-4e6f-a4e8-469f441258e0
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Compilerfehler C2326
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"Deklarator": Funktion kann nicht auf "Name" zugreifen  
  
 Der Code versucht, eine Membervariable zu ändern, was nicht möglich ist.  
  
## Beispiel  
 Im folgenden Beispiel wird C2326 generiert:  
  
```  
// C2326.cpp void MyFunc() { int i; class MyClass  { public: void mf() { i = 4;   // C2326 i is inaccessible } }; }  
```