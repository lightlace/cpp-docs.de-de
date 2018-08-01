---
title: __ptr32, __ptr64 | Microsoft-Dokumentation
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
ms.openlocfilehash: 050317be4c5f933ca9e08055a02555f5597c583c
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/01/2018
ms.locfileid: "39406532"
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