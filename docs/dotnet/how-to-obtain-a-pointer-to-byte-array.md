---
title: 'Vorgehensweise: Abrufen eines Zeigers auf Bytearray | Microsoft-Dokumentation'
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
ms.openlocfilehash: c20449a5e02e7743999d02f6a03254976e58fcfb
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46429291"
---
# <a name="how-to-obtain-a-pointer-to-byte-array"></a>Gewusst wie: Abrufen eines Zeigers auf ein Byte-Array

Sie erhalten einen Zeiger auf den Array-Block in einem <xref:System.Byte> Array durch das Übernehmen der Adresse des ersten Elements, und in einen Zeiger zuweisen.

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