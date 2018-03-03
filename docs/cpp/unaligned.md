---
title: __unaligned | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- __unaligned_cpp
dev_langs:
- C++
helpviewer_keywords:
- __unaligned keyword [C++]
ms.assetid: 0cd83aad-1840-47e3-ad33-59bfcbe6375b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: da662cf9cbe17539381766d37255e63d958fb7b1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="unaligned"></a>__unaligned
Wenn Sie einen Zeiger mit dem `__unaligned`-Modifizierer deklarieren, geht der Compiler davon aus, dass der Zeiger auf Daten verweist, die nicht ausgerichtet sind. Aus diesem Grund erstellt der Compiler für eine Anwendung, die auf einen Computer der Itanium-Prozessorfamilie (IPF) ausgerichtet ist, Code, der die nicht ausgerichteten Daten ein Byte nach dem anderen liest.  
  
## <a name="remarks"></a>Hinweise  
 Die `__unaligned` Modifizierer ist gültig für die [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)] und [!INCLUDE[vcpritanium](../cpp/includes/vcpritanium_md.md)] Compiler aber betrifft nur Anwendungen, die auf einen IPF-Computer ausgerichtet. Dieser Modifizierer beschreibt nur die Ausrichtung der adressierten Daten. Für den Zeiger selbst wird angenommen, dass er bereits ausgerichtet ist.  
  
 Die [!INCLUDE[vcpritanium](../cpp/includes/vcpritanium_md.md)] Prozessor generiert einen Ausrichtungsfehler, wenn er auf falsch ausgerichtete Daten zugreift, und die Zeit für den Fehler zu verarbeiten, mindert die Leistung. Verwenden Sie den `__unaligned`-Modifizierer, um den Prozessor zu veranlassen, die Daten ein Byte nach dem anderen zu lesen und so den Fehler zu vermeiden. Dieser Modifizierer ist nicht erforderlich für [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)] Anwendungen da die [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)] -Prozessor falsch ausgerichtete Daten ohne Fehler verarbeiten kann.  
  
 Weitere Informationen zur Ausrichtung finden Sie unter:  
  
-   [align](../cpp/align-cpp.md)  
  
-   [__alignof-Operator](../cpp/alignof-operator.md)  
  
-   [pack](../preprocessor/pack.md)  
  
-   [/ Zp (Strukturmembers)](../build/reference/zp-struct-member-alignment.md)  
  
-   [Beispiele für die Strukturausrichtung](../build/examples-of-structure-alignment.md)  
  
## <a name="example"></a>Beispiel  
  
```  
// unaligned_keyword.cpp  
// compile with: /c  
// processor: x64 IPF  
#include <stdio.h>  
int main() {  
   char buf[100];  
  
   int __unaligned *p1 = (int*)(&buf[37]);  
   int *p2 = (int *)p1;  
  
   *p1 = 0;   // ok  
  
   __try {  
      *p2 = 0;  // throws an exception  
   }  
   __except(1) {  
      puts("exception");  
   }  
}  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Schlüsselwörter](../cpp/keywords-cpp.md)