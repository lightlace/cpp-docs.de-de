---
title: "Compilerfehler C2734 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2734"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2734"
ms.assetid: e53a77b7-825c-42d1-a655-90e1c93b833e
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Compilerfehler C2734
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Bezeichner': Konstantes Objekt muss initialisiert werden, wenn es nicht extern ist  
  
 Der Bezeichner ist als `const` deklariert, wurde jedoch nicht initialisiert oder ist nicht `extern`.  
  
 Im folgenden Beispiel wird C2734 generiert:  
  
```  
// C2734.cpp  
const int j;   // C2734  
extern const int i;   // OK, declared as extern  
```