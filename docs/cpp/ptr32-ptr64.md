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
ms.openlocfilehash: 957e0deba31552777ef5e738afef13d74a640a18
ms.sourcegitcommit: a5fa9c6f4f0c239ac23be7de116066a978511de7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/20/2019
ms.locfileid: "75301326"
---
# <a name="__ptr32-__ptr64"></a>__ptr32, __ptr64

**Microsoft-spezifisch**

**__ptr32** stellt einen systemeigenen Zeiger auf einem 32-Bit-System dar, während **__ptr64** einen systemeigenen Zeiger auf einem 64-Bit-System darstellt.

Das folgende Beispiel zeigt, wie die einzelnen Zeigertypen deklariert werden:

```cpp
int * __ptr32 p32;
int * __ptr64 p64;
```

Auf einem 32-Bit-System wird ein Zeiger, der mit **__ptr64** deklariert ist, auf einen 32-Bit-Zeiger abgeschnitten. Auf einem 64-Bit-System wird ein Zeiger, der mit **__ptr32** deklariert wird, in einen 64-Bit-Zeiger umgewandelt.

> [!NOTE]
> Beim Kompilieren mit **/clr: pure**können **__ptr32** oder **__ptr64** nicht verwendet werden. Andernfalls wird der Compilerfehler C2472 generiert. Die Compileroptionen **/clr: pure** und **/clr: Safe** sind in Visual Studio 2015 veraltet und werden in Visual Studio 2017 nicht unterstützt.

Aus Kompatibilitätsgründen mit früheren Versionen sind **_ptr32** und **_ptr64** Synonyme für **__ptr32** und **__ptr64** , es sei denn, die Compileroption [/Za \(Deaktivieren von Spracherweiterungen)](../build/reference/za-ze-disable-language-extensions.md) ist angegeben.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird gezeigt, wie Zeiger mit den Schlüsselwörtern **__ptr32** und **__ptr64** deklariert und zuzuordnen sind.

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

[Integrierte Typen](../cpp/fundamental-types-cpp.md)