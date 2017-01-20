---
title: "Compilerfehler C2957"
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
  - "C2957"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2957"
ms.assetid: 9cb4526f-4af8-47e9-b786-56192627ca72
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2957
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"delim": Ungültiges linkes Trennzeichen: "\<" wurde erwartet.  
  
 Eine generische Klasse wurde nicht ordnungsgemäß formatiert.  
  
 Im folgenden Beispiel wird C2957 generiert:  
  
```  
// C2957.cpp // compile with: /clr /LD generic << class T>   // C2957 // try the following line instead // generic < class T> gc class C {};  
```