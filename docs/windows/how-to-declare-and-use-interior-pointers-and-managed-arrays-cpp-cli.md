---
title: 'Vorgehensweise: Deklarieren und Verwenden von inneren Zeigern und verwalteten Arrays (C + c++ / CLI) | Microsoft Docs'
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
ms.openlocfilehash: 457cec66aaabb01b9c10ccc66a8f9594312195b4
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33875304"
---
# <a name="how-to-declare-and-use-interior-pointers-and-managed-arrays-ccli"></a>Gewusst wie: Deklarieren und Verwenden von inneren Zeigern und verwalteten Arrays (C++/CLI)
Die folgenden C + c++ / CLI-Beispiel wird gezeigt, wie Sie deklarieren und einen inneren Zeiger auf ein Array verwenden können.  
  
> [!IMPORTANT]
>  Diese Sprachfunktion wird unterstützt, indem Sie die **"/ CLR"** (Compileroption), jedoch nicht von der **/Zw** -Compileroption.  
  
## <a name="example"></a>Beispiel  
  
### <a name="code"></a>Code  
  
```  
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
  
```  
1st element in arr holds: 1  
ipi points to memory address whose value is: 1  
after incrementing ipi, it points to memory address whose value is: 2  
```  
  
## <a name="see-also"></a>Siehe auch  
 [interior_ptr (C++/CLI)](../windows/interior-ptr-cpp-cli.md)