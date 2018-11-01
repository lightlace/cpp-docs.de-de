---
title: __ptr32, __ptr64
ms.date: 10/09/2018
f1_keywords:
- __ptr32_cpp
- __ptr64_cpp
- __ptr32
- __ptr64
- _ptr32
- _ptr64
helpviewer_keywords:
- __ptr64 keyword [C++]
- _ptr32 keyword [C++]
- ptr32 keyword [C++]
- ptr64 keyword [C++]
- _ptr64 keyword [C++]
- __ptr32 keyword [C++]
ms.assetid: afb563d8-7458-4fe7-9c30-bd4b5385a59f
ms.openlocfilehash: 0e979ed51f9c34700cef75113018c23e69a304f9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50588473"
---
# <a name="ptr32-ptr64"></a>__ptr32, __ptr64

**Microsoft-spezifisch**

**__ptr32** stellt einen systemeigenen Zeiger auf einem 32-Bit-System, während **__ptr64** einen systemeigenen Zeiger auf einem 64-Bit-System darstellt.

Das folgende Beispiel zeigt, wie die einzelnen Zeigertypen deklariert werden:

```cpp
int * __ptr32 p32;
int * __ptr64 p64;
```

Auf einem 32-Bit-System, ein Zeiger deklariert, mit **__ptr64** ist auf einen 32-Bit-Zeiger gekürzt. Auf einem 64-Bit-System, ein Zeiger deklariert, mit **__ptr32** in einen 64-Bit-Zeiger umgewandelt wird.

> [!NOTE]
> Sie können keine **__ptr32** oder **__ptr64** beim Kompilieren mit **/CLR: pure**. Andernfalls werden Compilerfehler C2472 generiert. Die **/CLR: pure** und **/CLR: safe** Compileroptionen in Visual Studio 2015 als veraltet markiert und in Visual Studio 2017 nicht unterstützt werden.

Für die Kompatibilität mit früheren Versionen **_ptr32** und **_ptr64** sind Synonyme für **__ptr32** und **__ptr64** , sofern-Compileroption [/Za \(spracherweiterungen deaktivieren)](../build/reference/za-ze-disable-language-extensions.md) angegeben ist.

## <a name="example"></a>Beispiel

Das folgende Beispiel zeigt, wie Sie deklarieren und Zuweisen von Zeigern mit dem **__ptr32** und **__ptr64** Schlüsselwörter.

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

[Grundlegende Typen](../cpp/fundamental-types-cpp.md)