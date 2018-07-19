---
title: Compilerwarnung (Stufe 1) C4067 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4067
dev_langs:
- C++
helpviewer_keywords:
- C4067
ms.assetid: 1d10353e-8cd5-4b01-9184-a06189b965a4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2ee6b48327e8754f9388e0df8f43009a5be70c97
ms.sourcegitcommit: 19a108b4b30e93a9ad5394844c798490cb3e2945
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/17/2018
ms.locfileid: "34255452"
---
# <a name="compiler-warning-level-1-c4067"></a>Compilerwarnung (Stufe 1) C4067

> Unerwartetes Token nach Präprozessordirektive - Zeilenvorschub erwartet

## <a name="remarks"></a>Hinweise

Der Compiler gefunden und zusätzliche Zeichen hinter einer Präprozessordirektive ignoriert. Dies kann durch eine unerwarteten Zeichen verursacht werden, obwohl eine häufige Ursache ein fehlgeleitetes Semikolon nach der Direktive ist. Kommentare führen nicht dazu, dass diese Warnung. Die **"/ Za"** -Compileroption kann diese Warnung für weitere Präprozessordirektiven als die Standardeinstellung.

## <a name="example"></a>Beispiel

```cpp
// C4067a.cpp
// compile with: cl /EHsc /DX /W1 /Za C4067a.cpp
#include <iostream>
#include <string> s     // C4067
#if defined(X);         // C4067
std::string s{"X is defined"};
#else
std::string s{"X is not defined"};
#endif;                 // C4067 only under /Za
int main()
{
    std::cout << s << std::endl;
}
```

Zur Behebung des Problems, löschen Sie die einzelnen Zeichen, oder verschieben sie in einem Kommentarblock. Bestimmte C4067 Warnungen werden möglicherweise deaktiviert, durch das Entfernen der **"/ Za"** -Compileroption.

```cpp
// C4067b.cpp
// compile with: cl /EHsc /DX /W1 C4067b.cpp
#include <iostream>
#include <string>
#if defined(X)
std::string s{"X is defined"};
#else
std::string s{"X is not defined"};
#endif
int main()
{
    std::cout << s << std::endl;
}
```