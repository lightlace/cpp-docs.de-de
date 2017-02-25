---
title: "Compilerfehler C2082 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C2082"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2082"
ms.assetid: 87a6d442-157c-46e8-9bff-8388f8338ae0
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Compilerfehler C2082
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Neudefinition des formalen Parameters "Bezeichner"  
  
 Ein formaler Parameter einer Funktion wird im Funktionsrumpf erneut deklariert. Um den Fehler zu beheben, entfernen Sie die Neudefinition.  
  
 Im folgenden Beispiel wird C2082 generiert.  
  
```  
// C2082.cpp void func(int i) { int i;   // C2082 int ii;   // OK }  
```