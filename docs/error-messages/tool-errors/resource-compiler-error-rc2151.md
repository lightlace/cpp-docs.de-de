---
title: "Ressourcencompiler: Fehler RC2151 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "RC2151"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "RC2151"
ms.assetid: 3c47e535-c78d-4338-aab9-9b47e2c34728
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Ressourcencompiler: Fehler RC2151
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Zeichenfolgenkonstanten können nicht wiederverwendet werden  
  
 In einer STRINGTABLE\-Anweisung wird zweimal derselbe Wert verwendet.  Stellen Sie sicher, dass keine überlappenden dezimalen und hexadezimalen Werte verwendet werden.  
  
 Jede ID in einer **STRINGTABLE** muss eindeutig sein.  Um größte Effizienz zu erzielen, verwenden Sie aufeinander folgende Konstanten, die bei einem Vielfachen von 16 beginnen.