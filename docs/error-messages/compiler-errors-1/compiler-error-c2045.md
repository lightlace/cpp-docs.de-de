---
title: "Compilerfehler C2045"
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
  - "C2045"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2045"
ms.assetid: 2fca668e-9b20-4933-987a-18c0fd0187df
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2045
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Bezeichner': Neudefinition einer Bezeichnung  
  
 Die Bezeichnung wird vor mehreren Anweisungen in derselben Funktion angezeigt.  
  
 Im folgenden Beispiel wird C2045 generiert:  
  
```  
// C2045.cpp int main() { label: { } goto label; label: {}   // C2045 }  
```