---
title: Attributtypen der Parameter (C++ / CLI und C++ / CX)
ms.date: 10/12/2018
ms.topic: reference
helpviewer_keywords:
- custom attributes, parameter types
ms.assetid: d9f127a3-7f08-456f-acc6-256805632712
ms.openlocfilehash: 09a13fa2f8d6db89824262a921adb338b151c995
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50599328"
---
# <a name="attribute-parameter-types--ccli-and-ccx"></a>Attributtypen der Parameter (C++ / CLI und C++ / CX)

Werte für Attribute übergeben, müssen für den Compiler zum Zeitpunkt der Kompilierung bekannt sein.  Zuordnen von Parametern können die folgenden Typen entsprechen:

- **bool**

- **Char**, **unsigned Char**

- **short**, **unsigned short**

- **Int**, **ganze Zahl ohne Vorzeichen**

- **lange**, **unsigned long**

- **__int64**, **__int64 ohne Vorzeichen**

- **"float"**, **double**

- **wchar_t**

- `char*`, `wchar_t*` oder `System::String*`

- `System::Type ^`

- `System::Object ^`

- **enum**

## <a name="example"></a>Beispiel

### <a name="code"></a>Code

```cpp
// attribute_parameter_types.cpp
// compile with: /clr /c
using namespace System;
ref struct AStruct {};

[AttributeUsage(AttributeTargets::ReturnValue)]
ref struct Attr : public Attribute {
   Attr(AStruct ^ i){}
   Attr(bool i){}
   Attr(){}
};

ref struct MyStruct {
   static AStruct ^ x = gcnew AStruct;
   [returnvalue:Attr(x)] int Test() { return 0; }   // C3104
   [returnvalue:Attr] int Test2() { return 0; }   // OK
   [returnvalue:Attr(true)] int Test3() { return 0; }   // OK
};
```

## <a name="example"></a>Beispiel

### <a name="description"></a>Beschreibung

Wenn Sie Attribute angeben, müssen alle unbenannten (Positions-) Argumente vor benannten Argumenten stehen.

### <a name="code"></a>Code

```cpp
// extending_metadata_c.cpp
// compile with: /clr /c
using namespace System;
[AttributeUsage(AttributeTargets::Class)]
ref class MyAttr : public Attribute {
public:
   MyAttr() {}
   MyAttr(int i) {}
   property int Priority;
   property int Version;
};

[MyAttr]
ref class ClassA {};   // No arguments

[MyAttr(Priority = 1)]
ref class ClassB {};   // Named argument

[MyAttr(123)]
ref class ClassC {};   // Positional argument

[MyAttr(123, Version = 1)]
ref class ClassD {};   // Positional and named
```

## <a name="example"></a>Beispiel

### <a name="description"></a>Beschreibung

Zuordnen von Parametern können eindimensionale Arrays der vorherigen Typen sein.

### <a name="code"></a>Code

```cpp
// extending_metadata_d.cpp
// compile with: /clr /c
using namespace System;

[AttributeUsage(AttributeTargets::Class)]
public ref struct ABC : public Attribute {
   ABC(array<int>^){}
   array<double> ^ param;
};

[ABC( gcnew array<int> {1,2,3}, param = gcnew array<double>{2.71, 3.14})]
ref struct AStruct{};
```

## <a name="see-also"></a>Siehe auch

[Benutzerdefinierte Attribute](../windows/user-defined-attributes-cpp-component-extensions.md)