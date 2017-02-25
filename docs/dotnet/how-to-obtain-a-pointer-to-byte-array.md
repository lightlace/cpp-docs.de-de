---
title: "Gewusst wie: Abrufen eines Zeigers auf ein Byte-Array | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "get-started-article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Bytearrays"
  - "Zeiger, Auf Bytearray"
ms.assetid: aea18073-3341-47f4-9f0e-04e03327037e
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
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