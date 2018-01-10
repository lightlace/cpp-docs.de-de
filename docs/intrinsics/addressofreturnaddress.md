---
title: _AddressOfReturnAddress | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- _AddressOfReturnAddress_cpp
- _AddressOfReturnAddress
dev_langs: C++
helpviewer_keywords:
- _AddressOfReturnAddress intrinsic
- AddressOfReturnAddress intrinsic
ms.assetid: c7e10b8c-445e-4236-a602-e2d90200f70a
caps.latest.revision: "17"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 670a9f5786fbe8f8855e9b88e179d005ba8603de
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="addressofreturnaddress"></a>_AddressOfReturnAddress
**Microsoft-spezifisch**  
  
 Enthält die Adresse des Speicherorts, der die Absenderadresse für die aktuelle Funktion enthält. Diese Adresse kann nicht verwendet werden, um den Zugriff auf andere Speicher-Speicherorte (z. B. die Argumente der Funktion).  
  
## <a name="syntax"></a>Syntax  
  
```  
void * _AddressOfReturnAddress();  
```  
  
## <a name="requirements"></a>Anforderungen  
  
|Systemintern|Architektur|  
|---------------|------------------|  
|`_AddressOfReturnAddress`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Headerdatei** \<intrin.h >  
  
## <a name="remarks"></a>Hinweise  
 Wenn `_AddressOfReturnAddress` wird verwendet, in einem Programm kompiliert mit ["/ CLR"](../build/reference/clr-common-language-runtime-compilation.md), die Funktion mit der `_AddressOfReturnAddress` Aufruf als eine systemeigene Funktion kompiliert wird. Wenn eine Funktion kompiliert, als verwaltete Aufrufe an die Funktion mit `_AddressOfReturnAddress`, `_AddressOfReturnAddress` Verhalten sich möglicherweise nicht wie erwartet.  
  
 Diese Routine ist nur als systeminterne Funktion verfügbar.  
  
## <a name="example"></a>Beispiel  
  
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
  
```Output  
0012FF78  
00401058  
00401058  
```  
  
**Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)   
 [Schlüsselwörter](../cpp/keywords-cpp.md)