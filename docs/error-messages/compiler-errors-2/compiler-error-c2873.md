---
title: "Compilerfehler C2873"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "error-reference"
f1_keywords: 
  - "C2873"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2873"
ms.assetid: 7a10036b-400e-4364-bd2f-dcd7370c5e28
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2873
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Symbol': Das Symbol kann nicht in einer using\-Deklaration verwendet werden  
  
 In einer `using`\-Direktive fehlt ein [namespace](../../misc/namespace-declaration.md)\-Schlüsselwort.  Dadurch wird der Code vom Compiler fälschlicherweise als [using\-Deklaration](../../cpp/using-declaration.md) und nicht als [using\-Direktive](../../misc/using-directive-cpp.md) interpretiert.