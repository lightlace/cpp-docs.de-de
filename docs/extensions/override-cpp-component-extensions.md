---
title: override (C++/CLI und C++/CX)
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- overriding, override keyword [C++]
- override keyword [C++]
ms.assetid: 34d19257-1686-4fcd-96f5-af07c70ba914
ms.openlocfilehash: 8dc7a0a0e6cf759d956fd701d033bd773e572af3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "65515655"
---
# <a name="override--ccli-and-ccx"></a>override (C++/CLI und C++/CX)

Das kontextbezogene **override**-Schlüsselwort gibt an, dass ein Member eines Typs eine Basisklasse oder einen Basisschnittstellen-Member überschreibt.

## <a name="remarks"></a>Anmerkungen

Das **override**-Schlüsselwort ist beim Kompilieren für native Ziele (standardmäßige Compileroption), für Windows-Runtime-Ziele (`/ZW`-Compileroption) oder Common Language Runtime-Ziele (`/clr`-Compileroption) gültig.

Weitere Informationen zu Überschreibungsspezifizierern finden Sie unter [Überschreibungsspezifizierer](../cpp/override-specifier.md) und [Überschreibungsspezifizierer und native Kompilierungen](../dotnet/how-to-declare-override-specifiers-in-native-compilations-cpp-cli.md).

Weitere Informationen zu kontextbezogenen Schlüsselwörtern finden Sie unter [Kontextbezogene Schlüsselwörter](context-sensitive-keywords-cpp-component-extensions.md).

## <a name="examples"></a>Beispiele

Das folgende Codebeispiel zeigt, dass **Überschreiben** auch in nativen Kompilierungen verwendet werden kann.

```cpp
// override_keyword_1.cpp
// compile with: /c
struct I1 {
   virtual void f();
};

struct X : public I1 {
   virtual void f() override {}
};
```

### <a name="example"></a>Beispiel

Das folgende Codebeispiel zeigt, dass **Überschreiben** auch in Windows-Runtime-Kompilierungen verwendet werden kann.

```cpp
// override_keyword_2.cpp
// compile with: /ZW /c
ref struct I1 {
   virtual void f();
};

ref struct X : public I1 {
   virtual void f() override {}
};
```

#### <a name="requirements"></a>Anforderungen

Compileroption: `/ZW`

### <a name="example"></a>Beispiel

Das folgende Codebeispiel zeigt, dass **Überschreiben** auch in Common Language Runtime-Kompilierungen verwendet werden kann.

```cpp
// override_keyword_3.cpp
// compile with: /clr /c
ref struct I1 {
   virtual void f();
};

ref struct X : public I1 {
   virtual void f() override {}
};
```

#### <a name="requirements"></a>Anforderungen

Compileroption: `/clr`

## <a name="see-also"></a>Siehe auch

[override-Bezeichner](../cpp/override-specifier.md)<br/>
[Überschreibungsspezifizierer](override-specifiers-cpp-component-extensions.md)