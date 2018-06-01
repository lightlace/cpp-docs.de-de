---
title: __ptr32, __ptr64 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- __ptr32_cpp
- __ptr64_cpp
dev_langs:
- C++
helpviewer_keywords:
- __ptr64 keyword [C++]
- _ptr32 keyword [C++]
- ptr32 keyword [C++]
- ptr64 keyword [C++]
- _ptr64 keyword [C++]
- __ptr32 keyword [C++]
ms.assetid: afb563d8-7458-4fe7-9c30-bd4b5385a59f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5746c8f54a51e24bad23dcb66f6648266e2e4b56
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/01/2018
ms.locfileid: "34704814"
---
# <a name="ptr32-ptr64"></a>__ptr32, __ptr64

**Microsoft-spezifisch**

`__ptr32` stellt einen systemeigenen Zeiger auf einem 32-Bit-System dar, während `__ptr64` einen systemeigenen Zeiger auf einem 64-Bit-System darstellt.

Das folgende Beispiel zeigt, wie die einzelnen Zeigertypen deklariert werden:

```cpp
int * __ptr32 p32;
int * __ptr64 p64;
```

 Bei einem 32-Bit-System wird ein Zeiger, der mit `__ptr64` deklariert wird, auf einen 32-Bit-Zeiger gekürzt. Bei einem 64-Bit-System wird ein Zeiger, der mit `__ptr32` deklariert wird, in einen 64-Bit-Zeiger umgewandelt.

> [!NOTE]
> Sie können keine `__ptr32` oder `__ptr64` beim Kompilieren mit **/CLR: pure**. Andernfalls werden Compilerfehler C2472 generiert werden. Die **/CLR: pure** und **/CLR: safe** Compileroptionen in Visual Studio 2015 als veraltet markiert und in Visual Studio 2017 nicht unterstützt werden.

## <a name="example"></a>Beispiel

Das folgende Beispiel zeigt, wie Zeiger mit den Schlüsselwörtern `__ptr32` und `__ptr64` deklariert und zugewiesen werden.

```cpp
#include <cstdlib>
#include <iostream>

int main()
{
    using namespace std;

    int * __ptr32 p32;
    int * __ptr64 p64;

    p32 = (int * __ptr32)malloc(4);
    *p32 = 32;
    cout << *p32 << endl;

    p64 = (int * __ptr64)malloc(4);
    *p64 = 64;
    cout << *p64 << endl;
}
```

```Output
32
64
```

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

- [Grundlegende Typen](../cpp/fundamental-types-cpp.md)