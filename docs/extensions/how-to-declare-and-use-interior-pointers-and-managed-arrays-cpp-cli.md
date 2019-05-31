---
title: 'Vorgehensweise: Deklarieren und Verwenden von inneren Zeigern und verwalteten Arrays (C++/CLI)'
ms.date: 10/12/2018
ms.topic: reference
helpviewer_keywords:
- pointers, interior
- arrays [C++], managed
ms.assetid: e61a2c09-a7d0-4867-91ea-6b8788a01079
ms.openlocfilehash: 0f7ec6551b09b2125fdb21736a851dae0dadbd4a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "65516335"
---
# <a name="how-to-declare-and-use-interior-pointers-and-managed-arrays-ccli"></a>Vorgehensweise: Deklarieren und Verwenden von inneren Zeigern und verwalteten Arrays (C++/CLI)

Das folgende C++/CLI-Beispiel zeigt, wie Sie einen inneren Zeiger auf ein Array deklarieren und verwenden können.

> [!IMPORTANT]
> Dieses Sprachfeature wird durch die Compileroption `/clr` unterstützt, nicht jedoch durch die Compileroption `/ZW`.

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

```Output
1st element in arr holds: 1
ipi points to memory address whose value is: 1
after incrementing ipi, it points to memory address whose value is: 2
```

## <a name="see-also"></a>Siehe auch

[interior_ptr (C++/CLI)](interior-ptr-cpp-cli.md)