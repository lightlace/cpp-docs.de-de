---
title: 'Vorgehensweise: Abrufen eines Zeigers auf Bytearray | Microsoft Docs'
ms.custom: get-started-article
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- pointers, to Byte array
- Byte arrays
ms.assetid: aea18073-3341-47f4-9f0e-04e03327037e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 1319da3f41903c469655cd533116de7a38d6b5b4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-obtain-a-pointer-to-byte-array"></a>Gewusst wie: Abrufen eines Zeigers auf ein Byte-Array
Sie erhalten einen Zeiger auf den Array-Block in ein <xref:System.Byte> Array nach Übernahme der Adresse des ersten Elements und einem Zeiger zuzuweisen.  
  
## <a name="example"></a>Beispiel  
  
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
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von C++-Interop (implizites PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)