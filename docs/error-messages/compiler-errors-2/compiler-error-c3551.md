---
title: "Compilerfehler C3551"
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
  - "C3551"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3551"
ms.assetid: c8ee23da-6568-40db-93a6-3ddb7ac47712
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3551
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"spät angegebener Rückgabetyp erwertet"  
  
 Wenn Sie das `auto`\-Schlüsselwort als Platzhalter für den Rückgabetyp einer Funktion verwenden, müssen Sie einen spät angegebenen Rückgabetyp angeben. Im folgenden Beispiel ist der spät angegebene Rückgabetyp der Funktion `myFunction` ein Zeiger auf ein Array mit vier Elementen vom Typ `int`.  
  
```  
auto myFunction()->int(*)[4];   
```  
  
## Siehe auch  
 [auto](../../cpp/auto-cpp.md)