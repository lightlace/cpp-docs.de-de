---
title: "Gewusst wie: Abrufen eines Zeigers auf ein Byte-Array"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "get-started-article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Bytearrays"
  - "Zeiger, Auf Bytearray"
ms.assetid: aea18073-3341-47f4-9f0e-04e03327037e
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# Gewusst wie: Abrufen eines Zeigers auf ein Byte-Array
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Sie können einen Zeiger auf den Array\-Block in einem <xref:System.Byte>\-Array abrufen, indem Sie die Adresse des ersten Elements nehmen, und diese einem Zeiger zuweisen.  
  
## Beispiel  
  
```  
// pointer_to_Byte_array.cpp  
// compile with: /clr  
using namespace System;  
int main() {  
   Byte bArr[] = {1, 2, 3};  
   Byte* pbArr = &bArr[0];  
  
   array<Byte> ^ bArr2 = gcnew array<Byte>{1,2,3};  
   interior_ptr<Byte> pbArr2 = &bArr2[0];  
}  
```  
  
## Siehe auch  
 [Verwenden von C\+\+\-Interop \(implizites PInvoke\)](../dotnet/using-cpp-interop-implicit-pinvoke.md)