---
title: __uuidof-Operator
ms.date: 10/10/2018
f1_keywords:
- __LIBID_cpp
- __uuidof_cpp
- __uuidof
- _uuidof
helpviewer_keywords:
- __uuidof keyword [C++]
- __LIBID_ keyword [C++]
ms.assetid: badfe709-809b-4b66-ad48-ee35039d25c6
ms.openlocfilehash: a14ef9043ec2196ff930a37d0eff95e90024d3d5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62244156"
---
# <a name="uuidof-operator"></a>__uuidof-Operator

**Microsoft-spezifisch**

Ruft die GUID ab, die dem Ausdruck angefügt ist.

## <a name="syntax"></a>Syntax

```
__uuidof (expression)
```

## <a name="remarks"></a>Hinweise

Die *Ausdruck* kann ein Typname, Zeiger, Verweis oder Array dieses Typs aufweisen, eine Vorlage, die auf diese Typen oder eine Variable dieser Typen spezialisiert. Das Argument ist gültig, solange der Compiler es verwenden kann, um das angefügte GUID zu suchen.

Ist ein Sonderfall dieser systeminternen Funktion, wenn entweder **0** oder NULL als Argument angegeben wird. In diesem Fall **__uuidof** gibt eine GUID, die Nullen besteht.

Verwenden Sie dieses Schlüsselwort, um die an folgende Elemente angefügte GUID zu extrahieren:

- Ein Objekt durch die [Uuid](../cpp/uuid-cpp.md) erweitertes Attribut.

- Ein bibliotheksblock erstellt, mit der [Modul](../windows/attributes/module-cpp.md) Attribut.

> [!NOTE]
> In einem Debugbuild **__uuidof** immer Initialisiert ein Objekt dynamisch (zur Laufzeit). In einem Releasebuild **__uuidof** können statisch (zur Kompilierzeit) initialisieren ein Objekts.

Für die Kompatibilität mit früheren Versionen **_uuidof** ist ein Synonym für **__uuidof** , wenn Compileroption [/Za \(spracherweiterungen deaktivieren)](../build/reference/za-ze-disable-language-extensions.md) ist angegeben.

## <a name="example"></a>Beispiel

Mit dem folgenden Code (kompiliert mit "ole32.lib") wird das "uuid" eines Bibliotheksblocks angezeigt, der mit dem Modulattribut erstellt wird:

```cpp
// expre_uuidof.cpp
// compile with: ole32.lib
#include "stdio.h"
#include "windows.h"

[emitidl];
[module(name="MyLib")];
[export]
struct stuff {
   int i;
};

int main() {
   LPOLESTR lpolestr;
   StringFromCLSID(__uuidof(MyLib), &lpolestr);
   wprintf_s(L"%s", lpolestr);
   CoTaskMemFree(lpolestr);
}
```

## <a name="comments"></a>Kommentare

In Fällen, die den Namen der Bibliothek nicht mehr in deren Bereich ist, können Sie `__LIBID_` anstelle von **__uuidof**. Zum Beispiel:

```cpp
StringFromCLSID(__LIBID_, &lpolestr);
```

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Ausdrücke mit unären Operatoren](../cpp/expressions-with-unary-operators.md)<br/>
[Schlüsselwörter](../cpp/keywords-cpp.md)