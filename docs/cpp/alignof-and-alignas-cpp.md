---
title: "alignof und alignas (C++)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "language-reference"
dev_langs: 
  - "C++"
ms.assetid: 1d18aa8a-9621-4fb5-86e5-4cc86d5187f4
caps.latest.revision: 2
caps.handback.revision: "2"
ms.author: "mblome"
manager: "ghogen"
---
# alignof und alignas (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Der `alignas`\-Typspezifizierer ist eine portierbare, in C\+\+ standardmäßige Art und Weise, die benutzerdefinierte Ausrichtung von Variablen und benutzerdefinierte Typen anzugeben.  Der `alignof`\-Operator ist ebenfalls eine standardmäßige, portierbare Art und Weise, die Ausrichtung eines angegebenen Typs oder einer Variable abzurufen.  
  
## Beispiel  
 Sie können `alignas` in einer Klasse oder in einzelnen Membern verwenden.  Werden mehrere `alignas`\-Spezifizierer gefunden, wählt der Compiler den strengsten davon aus \(denjenigen mit dem größten Wert\).  
  
```  
struct alignas(16) Bar  
{      
    int i;       // 4 bytes  
    int n;      // 4 bytes  
    alignas(4) char arr[3];  
    short s;          // 2 bytes  
};  
…  
cout << alignof(Bar) << endl; // output: 16  
  
```  
  
## Siehe auch  
 [Ausrichtung](../cpp/alignment-cpp-declarations.md)