---
title: "Compilerfehler C2871 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2871"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2871"
ms.assetid: 44aeb84d-61f0-45e0-8dad-22a3cd46b7f8
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# Compilerfehler C2871
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Name': Es ist kein Namespace mit diesem Namen vorhanden  
  
 Dieser Fehler tritt auf, wenn ein Bezeichner, der kein Namespace ist, an eine [using](../Topic/using%20Directive%20\(C%23%20Reference\).md)\-Direktive übergeben wird.  
  
 Im folgenden Beispiel wird C2871 generiert:  
  
```  
// C2871.cpp  
// compile with: /c  
using namespace d;   // C2871 d is not a namespace  
using namespace System;   // OK  
```