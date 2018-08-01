---
title: Alignof und Alignas (C++) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: 1d18aa8a-9621-4fb5-86e5-4cc86d5187f4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c10821f7e71c928fa749c2b85bd076cb9af6d04a
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/01/2018
ms.locfileid: "39402415"
---
# <a name="alignof-and-alignas-c"></a>alignof und alignas (C++)
Die **Alignas** Typspezifizierer ist eine portierbare, C++-Standardmethode, die eine benutzerdefinierte Ausrichtung von Variablen und benutzerdefinierte Typen anzugeben. Die **"alignof"** -Operator ist ebenfalls eine standardmäßige, portierbare Möglichkeit, die Ausrichtung eines angegebenen Typs oder einer Variablen zu erhalten.  
  
## <a name="example"></a>Beispiel  
 Sie können **Alignas** auf eine Klasse union, oder auf einzelne Elemente. Wenn mehrere **Alignas** Spezifizierer gefunden, wählt der Compiler den strengsten davon aus (denjenigen mit dem größten Wert) wählen.  
  
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