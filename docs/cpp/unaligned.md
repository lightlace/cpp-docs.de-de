---
title: "__unaligned"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "language-reference"
f1_keywords: 
  - "__unaligned_cpp"
  - "__unaligned"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__unaligned-Schlüsselwort [C++]"
ms.assetid: 0cd83aad-1840-47e3-ad33-59bfcbe6375b
caps.latest.revision: 11
caps.handback.revision: "11"
ms.author: "mblome"
manager: "ghogen"
---
# __unaligned
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wenn Sie einen Zeiger mit dem `__unaligned`\-Modifizierer deklarieren, geht der Compiler davon aus, dass der Zeiger auf Daten verweist, die nicht ausgerichtet sind.  Aus diesem Grund erstellt der Compiler für eine Anwendung, die auf einen Computer der Itanium\-Prozessorfamilie \(IPF\) ausgerichtet ist, Code, der die nicht ausgerichteten Daten ein Byte nach dem anderen liest.  
  
## Hinweise  
 Der `__unaligned`\-Modifizierer ist für die [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]\- und [!INCLUDE[vcpritanium](../cpp/includes/vcpritanium_md.md)]\-Compiler gültig, wirkt sich jedoch nur auf Anwendungen aus, die auf einen IPF\-Computer ausgerichtet sind.  Dieser Modifizierer beschreibt nur die Ausrichtung der adressierten Daten. Für den Zeiger selbst wird angenommen, dass er bereits ausgerichtet ist.  
  
 Der Prozessor [!INCLUDE[vcpritanium](../cpp/includes/vcpritanium_md.md)] generiert einen Ausrichtungsfehler, wenn er auf falsch ausgerichtete Daten zugreift, und die Zeit, um den Fehler zu verarbeiten, mindert die Leistung.  Verwenden Sie den `__unaligned`\-Modifizierer, um den Prozessor zu veranlassen, die Daten ein Byte nach dem anderen zu lesen und so den Fehler zu vermeiden.  Dieser Modifizierer ist für [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]\-Anwendungen nicht erforderlich, da der [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]\-Prozessor falsch ausgerichtete Daten ohne Fehler verarbeiten kann.  
  
 Weitere Informationen zur Ausrichtung finden Sie unter:  
  
-   [align](../cpp/align-cpp.md)  
  
-   [\_\_alignof\-Operator](../cpp/alignof-operator.md)  
  
-   [pack](../preprocessor/pack.md)  
  
-   [\/Zp \(Ausrichten des Strukturmembers\)](../build/reference/zp-struct-member-alignment.md)  
  
-   [Beispiele für die Strukturausrichtung](../build/examples-of-structure-alignment.md)  
  
## Beispiel  
  
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
  
## Siehe auch  
 [C\+\+\-Schlüsselwörter](../cpp/keywords-cpp.md)