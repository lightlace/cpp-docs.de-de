---
title: Alignof und Alignas (C++) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
ms.assetid: 1d18aa8a-9621-4fb5-86e5-4cc86d5187f4
caps.latest.revision: "2"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8a506a3c44c3304e786c41a2eb049939d317778e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="alignof-and-alignas-c"></a>alignof und alignas (C++)
Der `alignas`-Typspezifizierer ist eine portierbare, in C++ standardmäßige Art und Weise, die benutzerdefinierte Ausrichtung von Variablen und benutzerdefinierte Typen anzugeben. Der `alignof`-Operator ist ebenfalls eine standardmäßige, portierbare Art und Weise, die Ausrichtung eines angegebenen Typs oder einer Variable abzurufen.  
  
## <a name="example"></a>Beispiel  
 Sie können `alignas` in einer Klasse oder in einzelnen Membern verwenden. Werden mehrere `alignas`-Spezifizierer gefunden, wählt der Compiler den strengsten davon aus (denjenigen mit dem größten Wert).  
  
```cpp  
// alignas_alignof.cpp
// compile with: cl /EHsc alignas_alignof.cpp
#include <iostream>

struct alignas(16) Bar  
{      
    int i;       // 4 bytes  
    int n;      // 4 bytes  
    alignas(4) char arr[3];  
    short s;          // 2 bytes  
};  

int main()
{  
    std::cout << alignof(Bar) << std::endl; // output: 16  
}  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Ausrichtung](../cpp/alignment-cpp-declarations.md)