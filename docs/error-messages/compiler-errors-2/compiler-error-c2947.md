---
title: "Compilerfehler C2947 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2947"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2947"
ms.assetid: 6c056f62-ec90-4883-8a67-aeeb6ec13546
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# Compilerfehler C2947
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

erwartet '\>', um Konstrukt abzuschließen, Syntax "gefunden  
  
 Eine generische oder Vorlagenargumentliste wurde möglicherweise nicht ordnungsgemäß abgeschlossen.  
  
 C2947 kann auch durch Syntaxfehler verursacht werden.  
  
 Im folgenden Beispiel wird C2947 generiert:  
  
```  
// C2947.cpp  
// compile with: /c  
template <typename T>=   // C2947  
// try the following line instead  
// template <typename T>  
struct A {};  
```