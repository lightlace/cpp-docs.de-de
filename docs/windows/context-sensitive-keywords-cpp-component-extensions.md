---
title: Kontextbezogene Schlüsselwörter (C++ / CLI und C++ / CX) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 10/12/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- internal_CPP
dev_langs:
- C++
helpviewer_keywords:
- context-sensitive keywords
ms.assetid: e33da089-f434-44e9-8cce-4668d05a8939
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 5d02939e61da4a247b46da5637c38d01e7990c49
ms.sourcegitcommit: 3f4e92266737ecb70507871e87dc8e2965ad7e04
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/15/2018
ms.locfileid: "49327933"
---
# <a name="context-sensitive-keywords--ccli-and-ccx"></a>Kontextbezogene Schlüsselwörter (C++ / CLI und C++ / CX)

*Kontextbezogene Schlüsselwörter* sind Sprachelemente, die nur in bestimmten Kontexten erkannt werden. Außerhalb des jeweiligen Kontexts kann ein kontextbezogenes Schlüsselwort ein benutzerdefiniertes Symbol sein.

## <a name="all-runtimes"></a>Alle Laufzeiten

### <a name="remarks"></a>Hinweise

Die folgende Liste enthält die kontextbezogenen Schlüsselwörter:

- [abstract](../windows/abstract-cpp-component-extensions.md)

- [delegate](../windows/delegate-cpp-component-extensions.md)

- [event](../windows/event-cpp-component-extensions.md)

- [finally](../dotnet/finally.md)

- [for each in](../dotnet/for-each-in.md)

- [initonly](../dotnet/initonly-cpp-cli.md)

- `internal`

- [literal](../windows/literal-cpp-component-extensions.md)

- [override](../windows/override-cpp-component-extensions.md)

- [Eigenschaft](../windows/property-cpp-component-extensions.md)

- [sealed](../windows/sealed-cpp-component-extensions.md)

- `where` (Teil der [Generika](../windows/generics-cpp-component-extensions.md))

Für die Lesbarkeit zu erhöhen sollten Sie die Verwendung von kontextbezogenen Schlüsselwörtern als benutzerdefinierte Symbole einschränken.

## <a name="windows-runtime"></a>Windows-Runtime

### <a name="remarks"></a>Hinweise

(Es gibt keine plattformspezifischen Hinweise für diese Funktion.)

### <a name="requirements"></a>Anforderungen

Compileroption: `/ZW`

## <a name="common-language-runtime"></a>Common Language Runtime

### <a name="remarks"></a>Hinweise

(Es gibt keine plattformspezifischen Hinweise für diese Funktion.)

### <a name="requirements"></a>Anforderungen

Compileroption: `/clr`

### <a name="examples"></a>Beispiele

Das folgende Codebeispiel zeigt, dass im geeigneten Kontext, der **Eigenschaft** kontextbezogenes Schlüsselwort kann verwendet werden, um eine Eigenschaft und eine Variable definieren.

```cpp
// context_sensitive_keywords.cpp
// compile with: /clr
public ref class C {
   int MyInt;
public:
   C() : MyInt(99) {}

   property int Property_Block {   // context-sensitive keyword
      int get() { return MyInt; }
   }
};

int main() {
   int property = 0;               // variable name
   C ^ MyC = gcnew C();
   property = MyC->Property_Block;
   System::Console::WriteLine(++property);
}
```

```Output
100
```

## <a name="see-also"></a>Siehe auch

[Komponentenerweiterungen für .NET- und UWP](../windows/component-extensions-for-runtime-platforms.md)