---
title: "Compilerfehler C2159"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "C2159"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2159"
ms.assetid: 925a2cbd-43c9-45ee-a373-84004350b380
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2159
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Mehr als eine Speicherklasse angegeben  
  
 Eine Deklaration enthält mehr als eine Speicherklasse.  
  
 Im folgenden Beispiel wird C2159 generiert:  
  
```  
// C2159.cpp // compile with: /c static int i;   // OK extern static int i;   // C2159  
```