---
title: Compilerwarnung C4984
ms.date: 08/19/2019
f1_keywords:
- C4984
helpviewer_keywords:
- C4984
ms.openlocfilehash: 91ae30018c7de633d8ba23d538b301ad4bbac984
ms.sourcegitcommit: 9d4ffb8e6e0d70520a1e1a77805785878d445b8a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/20/2019
ms.locfileid: "69632904"
---
# <a name="compiler-warning-c4984"></a>Compilerwarnung C4984

> "if constexpr" ist eine c++ 17-Spracherweiterung

## <a name="remarks"></a>Hinweise

Der Compiler hat einen `if constexpr` Ausdruck im Code gefunden, der mit dem standardmäßigen c++ 14-Standard kompiliert wurde. Dieser Ausdruck wird ab dem c++ 17-Standard angegeben. Wenn Sie die Kompatibilität mit c++ 11 oder c++ 14 benötigen, ist dieser Ausdruck nicht portabel.

C4984 wird standardmäßig als Fehler ausgegeben, kann jedoch unterdrückt werden. Um diesen Ausdruck zu aktivieren, indem Sie Ihren Code als c++ 17 kompilieren, verwenden Sie [/Std: c++ 17 oder/Std: C + + Latest](../../build/reference/std-specify-language-standard-version.md). Um den `if constexpr` Ausdruck in Code zu verwenden, der für c++ 14 als Microsoft-Erweiterung kompiliert wurde, können Sie die Warnstufe der Fehlermeldung unterdrücken, deaktivieren oder ändern. Sie können [/wd4984](../../build/reference/compiler-option-warning-level.md) verwenden, um C4984 oder __/w__*N*__4984__ zu deaktivieren, um es als Warnung der Ebene *N* anstelle eines Fehlers zu aktivieren. Oder verwenden Sie [#pragma Warnung (unterdrücken: 4984)](../../preprocessor/warning.md) vor der Zeile, die die Warnung in der Quelldatei auslöst.

Diese Warnung ist ab Visual Studio 2017, Version 15,3, verfügbar. Informationen zum Deaktivieren von Warnungen, die in einer bestimmten Compilerversion oder höher eingeführt wurden, finden Sie unter Compilerwarnungen [by Compiler Version](compiler-warnings-by-compiler-version.md).

## <a name="example"></a>Beispiel

Dieses Beispiel generiert C4984 und zeigt Möglichkeiten, Sie zu beheben:

```cpp
// C4984.cpp
// compile with: cl /EHsc C4984.cpp
#include <iostream>

int main()
{
    constexpr bool compile_time = true;
    // Uncomment the following line or use /std:c++17 to fix
    // #pragma warning(suppress:4984)
    if constexpr (compile_time)
    {
        std::cout << "compile_time is true";
    }
    else
    {
        std::cout << "compile_time is false";
    }
}
```
