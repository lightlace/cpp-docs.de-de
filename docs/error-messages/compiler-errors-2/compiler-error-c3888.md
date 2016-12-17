---
title: "Compilerfehler C3888"
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
  - "C3888"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3888"
ms.assetid: 40820812-79c5-4dcd-a19d-b4164d25fc8a
caps.latest.revision: 3
caps.handback.revision: "3"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3888
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"name": Der diesem literal\-Datenmember zugeordnete Konstantenausdruck wird von C\+\+\/CLI nicht unterstützt  
  
 Das *name*\-Datenmember, das mit dem [literal](../../windows/literal-cpp-component-extensions.md)\-Schlüsselwort deklariert wird, wird mit einem Wert initialisiert, der vom Compiler nicht unterstützt wird. Der Compiler unterstützt nur konstante integrale, Enumerations\- oder Zeichenfolgentypen. Der Fehler **C3888** wurde wahrscheinlich dadurch verursacht, dass das Datenmember mit einem Bytearray initialisiert wird.  
  
### So beheben Sie diesen Fehler  
  
1.  Vergewissern Sie sich, dass das deklarierte literal\-Datenmember ein unterstützter Typ ist.  
  
## Siehe auch  
 [literal](../../windows/literal-cpp-component-extensions.md)