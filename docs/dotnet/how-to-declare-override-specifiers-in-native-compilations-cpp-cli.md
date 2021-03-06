---
title: 'Vorgehensweise: Deklarieren von Überschreibungsbezeichnern (C++ / CLI)'
ms.date: 11/04/2016
helpviewer_keywords:
- override specifiers in native compilation, overriding
ms.assetid: d0551836-9ac7-41eb-a6e9-a4b3ef60767d
ms.openlocfilehash: db74ef226242ec8f4f70f2769fbc8ba102a808c8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62387421"
---
# <a name="how-to-declare-override-specifiers-in-native-compilations-ccli"></a>Vorgehensweise: Deklarieren von Überschreibungsbezeichnern in nativen Kompilierungen (C++ / CLI)

[versiegelte](../extensions/sealed-cpp-component-extensions.md), [abstrakte](../extensions/abstract-cpp-component-extensions.md), und [überschreiben](../extensions/override-cpp-component-extensions.md) stehen in Kompilierungen, die keine **/Zw** oder ["/ CLR"](../build/reference/clr-common-language-runtime-compilation.md).

> [!NOTE]
>  Hat der ISO C ++ 11-Standardsprache der [außer Kraft setzen](../cpp/override-specifier.md) Bezeichner und die [endgültige](../cpp/final-specifier.md) Bezeichner, und beide werden in Visual Studio verwenden unterstützt `final` anstelle von `sealed` in Code, der zum vorgesehen ist als nur nativ kompiliert werden.

## <a name="example"></a>Beispiel

### <a name="description"></a>Beschreibung

Das folgende Beispiel zeigt, dass `sealed` in nativen Kompilierungen gültig ist.

### <a name="code"></a>Code

```cpp
// sealed_native_keyword.cpp
#include <stdio.h>
__interface I1 {
   virtual void f();
   virtual void g();
};

class X : public I1 {
public:
   virtual void g() sealed {}
};

class Y : public X {
public:

   // the following override generates a compiler error
   virtual void g() {}   // C3248 X::g is sealed!
};
```

## <a name="example"></a>Beispiel

### <a name="description"></a>Beschreibung

Das nächste Beispiel zeigt, dass `override` in nativen Kompilierungen gültig ist.

### <a name="code"></a>Code

```cpp
// override_native_keyword.cpp
#include <stdio.h>
__interface I1 {
   virtual void f();
};

class X : public I1 {
public:
   virtual void f() override {}   // OK
   virtual void g() override {}   // C3668 I1::g does not exist
};
```

## <a name="example"></a>Beispiel

### <a name="description"></a>Beschreibung

Dieses Beispiel zeigt, dass `abstract` in nativen Kompilierungen gültig ist.

### <a name="code"></a>Code

```cpp
// abstract_native_keyword.cpp
class X abstract {};

int main() {
   X * MyX = new X;   // C3622 cannot instantiate abstract class
}
```

## <a name="see-also"></a>Siehe auch

[Überschreibungsspezifizierer](../extensions/override-specifiers-cpp-component-extensions.md)
