---
title: "Compilerfehler C2045 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C2045"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2045"
ms.assetid: 2fca668e-9b20-4933-987a-18c0fd0187df
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Compilerfehler C2045
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Bezeichner': Neudefinition einer Bezeichnung  
  
 Die Bezeichnung wird vor mehreren Anweisungen in derselben Funktion angezeigt.  
  
 Im folgenden Beispiel wird C2045 generiert:  
  
```  
// C2045.cpp int main() { label: { } goto label; label: {}   // C2045 }  
```