---
title: "Compilerfehler C2465 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C2465"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2465"
ms.assetid: 65ba2a9f-d95e-4af3-b60b-1ac59a1e307c
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Compilerfehler C2465
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Definition anonymer Typen innerhalb von Klammern nicht möglich  
  
 Eine anonyme Struktur, Union oder ein Aufzählungstyp ist innerhalb eines in Klammern stehenden Ausdrucks definiert. Dies ist in C\+\+ ungültig, da die Definition im Funktionsbereich ohne Bedeutung ist.