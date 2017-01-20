---
title: "Compiler Error C3353"
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
  - "C3353"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3353"
ms.assetid: 5699c04b-d504-46ce-bf71-c200318fed71
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "corob"
manager: "ghogen"
---
# Compiler Error C3353
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Delegat': Ein Delegat kann nur von einer globalen Funktion oder einer Memberfunktion eines verwalteten oder WinRT\-Typs erstellt werden.  
  
 Delegaten, die mit dem Schlüsselwort [\_\_delegate](../../misc/delegate.md) oder [delegate](../../windows/delegate-cpp-component-extensions.md) deklariert werden, können nur im globalen Gültigkeitsbereich deklariert werden.  
  
 Im folgenden Beispiel wird C3353 generiert:  
  
```  
// C3353.cpp  
// compile with: /clr  
delegate int f;   // C3353  
```