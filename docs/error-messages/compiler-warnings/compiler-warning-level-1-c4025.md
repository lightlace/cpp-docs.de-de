---
title: "Compilerwarnung (Stufe 1) C4025 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4025"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4025"
ms.assetid: c4f6a651-0641-4446-973e-8290065e49ad
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Compilerwarnung (Stufe 1) C4025
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"Anzahl": Zeiger auf ein separates Segment an Funktion mit variablen Argumenten übergeben: Parameteranzahl  
  
 Die Übergabe eines basierten Zeigers an eine Funktion mit variablen Argumenten bewirkt, dass der Zeiger normalisiert wird. Dies kann unvorhersehbare Folgen haben. Übergeben Sie keine basierten Zeiger an Funktionen mit variablen Argumenten.