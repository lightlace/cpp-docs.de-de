---
title: 'Vorgehensweise: Durchlaufen von Arrays mit für die einzelnen | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- arrays [C++], iterating with for each
ms.assetid: ddc88ce2-69e1-44fc-af84-5b6f62fcb9e3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 5d16281d6ee53f8e426b92c60b41dcdcae200ba6
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46428368"
---
# <a name="how-to-iterate-over-arrays-with-for-each"></a>Gewusst wie: Durchlaufen von Arrays mit der for-each-Klausel

In diesem Thema wird gezeigt, wie Sie mit der [für jedes im](../dotnet/for-each-in.md) -Schlüsselwort in verschiedener Typen von Arrays.

## <a name="example"></a>Beispiel

Dieses Beispiel zeigt, wie Sie mit `for each` Array von Verweistypen.  Beachten Sie, dass, wenn eine bestimmte Dimension des ein eindimensionales Array mit mehreren 0 (null) ist, wird die `for each` Schleife wird nicht über das Array durchlaufen.

```
// for_each_arrays.cpp
// compile with: /clr
using namespace System;
ref struct MyClass {
   void Test() { Console::WriteLine("in MyClass"); }
};

ref struct MyClass2 {
   void Test() { Console::WriteLine("in MyClass2"); }
};

int main() {
   array<MyClass ^> ^ MyArray = gcnew array<MyClass ^>(2);

   int i = 0;
   for each ( MyClass ^ c in MyArray ) {
      Console::Write("{0} = ", i++);
      c -> Test();
   }

   Console::WriteLine();

   array< MyClass2 ^, 2 > ^ MyArray2 = gcnew array< MyClass2 ^, 2 >(2, 2);
   i = 0;
   for each ( MyClass2 ^ c in MyArray2 ) {
      Console::Write("{0} = ", i++);
      c -> Test();
   }

   array< MyClass2 ^, 2 > ^ MyArray3 = gcnew array< MyClass2 ^, 2 >(2, 0);
   i = 0;
   for each ( MyClass2 ^ c in MyArray3 ) {
      Console::Write("{0} = ", i++);
      c -> Test();
   }
}
```

```Output
0 = in MyClass
1 = in MyClass

0 = in MyClass2
1 = in MyClass2
2 = in MyClass2
3 = in MyClass2
```

## <a name="example"></a>Beispiel

Dieses Beispiel zeigt für jede Iteration über eine <xref:System.Collections.ArrayList>, implementiert <xref:System.Collections.IEnumerable>.

```
// for_each_arrays_2.cpp
// compile with: /clr
using namespace System;
using namespace System::Collections;

int main() {
   int retval = 0;

   ArrayList ^ arr = gcnew ArrayList();
   arr->Add(10);
   arr->Add(20);
   arr->Add(30);

   for each ( int c in arr )
      retval += c;
   Console::WriteLine(retval);
}
```

```Output
60
```

## <a name="example"></a>Beispiel

Dieses Beispiel zeigt, wie ein Array von Arrays durchlaufen wird.

```
// for_each_arrays_3.cpp
// compile with: /clr
using namespace System;

#define ARRAY_SIZE 2

int main() {
   int i, j;

   // Declares an array of managed arrays of Int32.
   array< array< Int32 > ^ > ^ IntArray = gcnew array<array< Int32 > ^>(ARRAY_SIZE);

   for (i = 0 ; i < ARRAY_SIZE ; i++) {
      IntArray[i] = gcnew array< Int32 >(ARRAY_SIZE);
         for ( int j = 0 ; j < ARRAY_SIZE ; j++ )
            IntArray[i][j] = i + 10;
   }

   for (i = 0 ; i < ARRAY_SIZE ; i++)
      for (int j = 0 ; j < ARRAY_SIZE ; j++)
         Console::WriteLine("IntArray[{0}] = {1}", i, IntArray[i][j]);
   Console::WriteLine();

   for each (array<Int32> ^ xyz in IntArray)
      for each ( int c in xyz )
         Console::WriteLine(c);
}
```

```Output
IntArray[0] = 10
IntArray[0] = 10
IntArray[1] = 11
IntArray[1] = 11

10
10
11
11
```

## <a name="see-also"></a>Siehe auch

[for each in](../dotnet/for-each-in.md)