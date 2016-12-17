---
title: "How to: Pin Pointers and Arrays"
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
helpviewer_keywords: 
  - "pointers, pinning"
  - "arrays [C++], pinning"
ms.assetid: ee783260-e676-46b8-a38e-11a06f1d57b0
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "mblome"
manager: "ghogen"
---
# How to: Pin Pointers and Arrays
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Das Fixieren eines Unterobjekts, das in einem verwalteten Objekt definiert wurde, hat den Auswirkungen des Anheftens des gesamten Objekts.  Beispielsweise, wenn überhaupt wird Arrayelement fixiert, wird das Ganzarray ebenfalls fixiert.  Es gibt keine Erweiterungen zur Sprache zum Deklarieren eines festen Arrays.  Um ein Array für, deklarieren einen festen Zeiger zu dessen Elementtyp und zu Pin einer seiner Elemente.  
  
## Beispiel  
  
### Code  
  
```  
// pin_ptr_array.cpp  
// compile with: /clr  
#include <stdio.h>  
using namespace System;  
  
int main() {  
   array<Byte>^ arr = gcnew array<Byte>(4);  
   arr[0] = 'C';  
   arr[1] = '+';  
   arr[2] = '+';  
   arr[3] = '\0';  
   pin_ptr<Byte> p = &arr[1];   // entire array is now pinned  
   unsigned char * cp = p;  
  
   printf_s("%s\n", cp); // bytes pointed at by cp  
                         // will not move during call  
}  
```  
  
### Ausgabe  
  
```  
++  
```  
  
## Siehe auch  
 [pin\_ptr \(C\+\+\/CLI\)](../windows/pin-ptr-cpp-cli.md)