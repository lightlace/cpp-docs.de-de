---
title: Explizite Überschreibungen (Komponentenerweiterungen für C++) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- overriding, override [C++]
ms.assetid: 4ec3eaf5-163b-4df8-8f16-7a2ec04c3d0f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 3ce2f65fd740fd2bf133d65b25cbb52838c53dd2
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42601211"
---
# <a name="explicit-overrides--c-component-extensions"></a>Explizite Überschreibungen (Komponentenerweiterungen für C++)

In diesem Thema wird erläutert, wie ein Member einer Basisklasse oder Schnittstelle explizit zu überschreiben. Benannte Überschreibung (explizite) sollte nur verwendet werden, um eine Methode mit einer abgeleiteten Methode überschreiben, die einen anderen Namen aufweist.

## <a name="all-runtimes"></a>Alle Laufzeiten

### <a name="syntax"></a>Syntax

```cpp
overriding-function-declarator = type::function [,type::function] { overriding-function-definition }
overriding-function-declarator = function { overriding-function-definition }
```

### <a name="parameters"></a>Parameter

*Überschreiben der funktionsdeklarator*  
Typ, Name und Argument Rückgabeliste der überschreibenden Funktion.  Beachten Sie, dass die überschreibende Funktion nicht unbedingt den gleichen Namen wie die überschriebene Funktion haben.

*Typ*  
Der Basistyp, der eine Funktion, die außer Kraft setzen enthält.

*function*  
Eine durch Trennzeichen getrennte Liste für eine oder mehrere Funktionsnamen zu überschreiben.

*Überschreiben der Funktionsdefinition*  
Die Funktion Text-Anweisungen, die die überschreibende Funktion zu definieren.

### <a name="remarks"></a>Hinweise

Explizite verwenden Sie Außerkraftsetzungen, um einen Alias für die Signatur einer Methode zu erstellen oder um unterschiedliche Implementierungen für Methoden Witht die gleiche Signatur bereitzustellen.

Informationen zum Ändern des Verhaltens von geerbten Typen geerbte Typ- und Typmemberdeklarationen finden Sie unter [Überschreibungsspezifizierer](../windows/override-specifiers-cpp-component-extensions.md).

## <a name="windows-runtime"></a>Windows-Runtime

### <a name="requirements"></a>Anforderungen

Compileroption: `/ZW`

## <a name="common-language-runtime"></a>Common Language Runtime

### <a name="remarks"></a>Hinweise

Informationen über explizite überschreibungen in nativem Code oder Code kompiliert wird, mit `/clr:oldSyntax`, finden Sie unter [explizite Überschreibungen](../cpp/explicit-overrides-cpp.md).

### <a name="requirements"></a>Anforderungen

Compileroption: `/clr`

### <a name="examples"></a>Beispiele

Das folgende Codebeispiel zeigt eine einfache, implizite Override "und" Implementierung eines Members in eine Basisschnittstelle, nicht über explizite überschreibungen.

```cpp
// explicit_override_1.cpp
// compile with: /clr
interface struct I1 {
   virtual void f();
};

ref class X : public I1 {
public:
   virtual void f() {
      System::Console::WriteLine("X::f override of I1::f");
   }
};

int main() {
   I1 ^ MyI = gcnew X;
   MyI -> f();
}
```

```Output
X::f override of I1::f
```

Im folgenden Codebeispiel wird veranschaulicht, wie alle Schnittstellenmember mit einer gemeinsamen Signatur, die mit der explizite Überschreibungssyntax implementiert wird.

```cpp
// explicit_override_2.cpp
// compile with: /clr
interface struct I1 {
   virtual void f();
};

interface struct I2 {
   virtual void f();
};

ref struct X : public I1, I2 {
   virtual void f() = I1::f, I2::f {
      System::Console::WriteLine("X::f override of I1::f and I2::f");
   }
};

int main() {
   I1 ^ MyI = gcnew X;
   I2 ^ MyI2 = gcnew X;
   MyI -> f();
   MyI2 -> f();
}
```

```Output
X::f override of I1::f and I2::f
X::f override of I1::f and I2::f
```

Im folgenden Codebeispiel wird veranschaulicht, wie eine Funktion zum Überschreiben von der Funktion einen anderen Namen haben kann, die implementiert wird.

```cpp
// explicit_override_3.cpp
// compile with: /clr
interface struct I1 {
   virtual void f();
};

ref class X : public I1 {
public:
   virtual void g() = I1::f {
      System::Console::WriteLine("X::g");
   }
};

int main() {
   I1 ^ a = gcnew X;
   a->f();
}
```

```Output
X::g
```

Das folgende Codebeispiel zeigt eine explizite schnittstellenimplementierung, die eine sichere Auflistung implementiert.

```cpp
// explicit_override_4.cpp
// compile with: /clr /LD
using namespace System;
ref class R : ICloneable {
   int X;

   virtual Object^ C() sealed = ICloneable::Clone {
      return this->Clone();
   }

public:
   R() : X(0) {}
   R(int x) : X(x) {}

   virtual R^ Clone() {
      R^ r = gcnew R;
      r->X = this->X;
      return r;
   }
};
```

## <a name="see-also"></a>Siehe auch

[Komponentenerweiterungen für Laufzeitplattformen](../windows/component-extensions-for-runtime-platforms.md)