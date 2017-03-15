---
title: "_AddressOfReturnAddress | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_AddressOfReturnAddress_cpp"
  - "_AddressOfReturnAddress"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_AddressOfReturnAddress intrinsic"
  - "AddressOfReturnAddress intrinsic"
ms.assetid: c7e10b8c-445e-4236-a602-e2d90200f70a
caps.latest.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 15
---
# _AddressOfReturnAddress
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Stellt die Adresse der Speicheradresse bereit, die die Rückgabeadresse der aktuellen Funktion enthält.  Diese Adresse kann nicht verwendet werden, um andere Speicherorte \(z. B. die Argumente der Funktion\) zuzugreifen.  
  
## Syntax  
  
```  
void * _AddressOfReturnAddress();  
```  
  
## Anforderungen  
  
|Intrinsisch|Architektur|  
|-----------------|-----------------|  
|`_AddressOfReturnAddress`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Headerdatei** \<intrin.h\>  
  
## Hinweise  
 Wenn `_AddressOfReturnAddress` in einem Programm verwendet wird, die mit [\/clr](../build/reference/clr-common-language-runtime-compilation.md)kompiliert wird, wird die Funktion, die den `_AddressOfReturnAddress` Aufruf enthält, als systemeigene Funktion kompiliert.  Wenn eine Funktion, die als verwaltete Aufrufe in die Funktion enthält `_AddressOfReturnAddress`kompiliert wird, `_AddressOfReturnAddress` sich nicht wie erwartet verhielte.  
  
 Diese Routine ist als systeminterne Funktion nur verfügbar.  
  
## Beispiel  
  
```  
// compiler_intrinsics_AddressOfReturnAddress.cpp  
// processor: x86, x64  
#include <stdio.h>  
#include <intrin.h>  
  
// This function will print three values:  
//   (1) The address retrieved from _AddressOfReturnAdress  
//   (2) The return address stored at the location returned in (1)  
//   (3) The return address retrieved the _ReturnAddress* intrinsic  
// Note that (2) and (3) should be the same address.  
__declspec(noinline)  
void func() {  
   void* pvAddressOfReturnAddress = _AddressOfReturnAddress();  
   printf_s("%p\n", pvAddressOfReturnAddress);  
   printf_s("%p\n", *((void**) pvAddressOfReturnAddress));  
   printf_s("%p\n", _ReturnAddress());  
}  
  
int main() {  
   func();  
}  
```  
  
  **0012FF78**  
**00401058**  
**00401058**   
## Microsoft ENDES bestimmten  
  
## Siehe auch  
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)   
 [C\+\+\-Schlüsselwörter](../cpp/keywords-cpp.md)