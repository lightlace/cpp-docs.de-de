---
title: Compilerwarnung (Stufe 3) C4580
ms.date: 11/04/2016
f1_keywords:
- C4580
helpviewer_keywords:
- C4580
ms.assetid: fef6e8e0-0d6a-44fa-b22a-2fe7ba2ef379
ms.openlocfilehash: bd2ecff5adc6538f75c61772b785acbfc89092ae
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2019
ms.locfileid: "58781769"
---
# <a name="compiler-warning-level-3-c4580"></a>Compilerwarnung (Stufe 3) C4580

[attribute] ist veraltet; geben Sie stattdessen System::Attribute oder Platform::Metadata als Basisklasse an.

[[Attribut](../../windows/attributes/attribute.md)] ist nicht mehr die bevorzugte Syntax zum Erstellen von benutzerdefinierten Attributen. Weitere Informationen finden Sie unter [User-Defined Attributes](../../extensions/user-defined-attributes-cpp-component-extensions.md). Leiten Sie für CLR-Code Attribute aus `System::Attribute` ab. Leiten Sie für Windows-Runtime-Code Attribute aus `Platform::Metadata` ab.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C3454 generiert und gezeigt, wie Sie diesen Fehler beheben.

```cpp
// C4580.cpp
// compile with: /W3 /c /clr
[attribute]   // C4580
public ref class Attr {
public:
   int m_t;
};

public ref class Attr2 : System::Attribute {
public:
   int m_t;
};
```