---
title: Attributparametertypen (C++/CLI und C++/CX)
ms.date: 10/12/2018
ms.topic: reference
helpviewer_keywords:
- custom attributes, parameter types
ms.assetid: d9f127a3-7f08-456f-acc6-256805632712
ms.openlocfilehash: fbb2bd68f589630608e341b944b4201c12d67211
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "65516175"
---
# <a name="attribute-parameter-types--ccli-and-ccx"></a>Attributparametertypen (C++/CLI und C++/CX)

An Attribute übergebene Werte müssen dem Compiler zum Zeitpunkt der Kompilierung bekannt sein.  Attributparameter können einen der folgenden Typen aufweisen:

- **bool**

- **char**, **unsigned char**

- **short**, **unsigned short**

- **int**, **unsigned int**

- **long**, **unsigned long**

- **__int64**, **unsigned __int64**

- **float**, **double**

- **wchar_t**

- `char*` oder `wchar_t*` oder `System::String*`

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

Wenn Sie Attribute angeben, müssen alle unbenannten (positionellen) Argumente vor benannten Argumenten stehen.

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

Attributparameter können eindimensionale Arrays der vorherigen Typen sein.

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

[Benutzerdefinierte Attribute](user-defined-attributes-cpp-component-extensions.md)