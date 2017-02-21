---
title: "Compilerwarnung (Stufe 4) C4057 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4057"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4057"
ms.assetid: e75d0645-84c9-4bef-a812-942ed9879aa3
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Compilerwarnung (Stufe 4) C4057
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Operator': 'Bezeichner1' Dereferenzierung in leicht unterschiedliche Basistypen von 'Bezeichner2'  
  
 Zwei Zeigerausdrücke verweisen auf unterschiedliche Basistypen. Die Ausdrücke werden ohne Konvertierung verwendet.  
  
### Dieser Fehler kann eine der folgenden Ursachen haben:  
  
1.  Typen mit und ohne Vorzeichen werden gemischt verwendet.  
  
2.  **short**\- und **long**\-Typen werden gemischt verwendet.