---
title: 'Vorgehensweise: Deklarieren und Verwenden von inneren Zeigern und verwalteten Arrays (C++ / CLI) | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- pointers, interior
- arrays [C++], managed
ms.assetid: e61a2c09-a7d0-4867-91ea-6b8788a01079
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 4c02849bc3d1b45ecb6de89e103c51311af31b3c
ms.sourcegitcommit: d5d6bb9945c3550b8e8864b22b3a565de3691fde
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/06/2018
ms.locfileid: "39569842"
---
# <a name="how-to-declare-and-use-interior-pointers-and-managed-arrays-ccli"></a>Gewusst wie: Deklarieren und Verwenden von inneren Zeigern und verwalteten Arrays (C++/CLI)
Der folgende C++-/ c++ / CLI-Beispiel wird gezeigt, wie Sie deklarieren und einen inneren Zeiger auf ein Array verwenden können.  
  
> [!IMPORTANT]
>  Diese Sprachfunktion wird unterstützt, indem die `/clr` -Compileroption verwenden, aber nicht von der `/ZW` -Compileroption.  
  
## <a name="example"></a>Beispiel  
  
### <a name="code"></a>Code  
  
```cpp  
// interior_ptr_arrays.cpp  
// compile with: /clr  
#define SIZE 10  
  
int main() {  
   // declare the array  
   array<int>^ arr = gcnew array<int>(SIZE);  
  
   // initialize the array  
   for (int i = 0 ; i < SIZE ; i++)  
      arr[i] = i + 1;  
  
   // create an interior pointer into the array  
   interior_ptr<int> ipi = &arr[0];  
  
   System::Console::WriteLine("1st element in arr holds: {0}", arr[0]);  
   System::Console::WriteLine("ipi points to memory address whose value is: {0}", *ipi);  
  
   ipi++;  
   System::Console::WriteLine("after incrementing ipi, it points to memory address whose value is: {0}", *ipi);  
}  
```  
  
### <a name="output"></a>Ausgabe  
  
```Output  
1st element in arr holds: 1  
ipi points to memory address whose value is: 1  
after incrementing ipi, it points to memory address whose value is: 2  
```  
  
## <a name="see-also"></a>Siehe auch  
 [interior_ptr (C++/CLI)](../windows/interior-ptr-cpp-cli.md)