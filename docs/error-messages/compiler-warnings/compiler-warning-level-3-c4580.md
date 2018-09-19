---
title: Compilerwarnung (Stufe 3) C4580 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4580
dev_langs:
- C++
helpviewer_keywords:
- C4580
ms.assetid: fef6e8e0-0d6a-44fa-b22a-2fe7ba2ef379
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3a9d25a77b6936a3b5b741a1da927c6beb24cbb1
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46072224"
---
# <a name="compiler-warning-level-3-c4580"></a>Compilerwarnung (Stufe 3) C4580

[attribute] ist veraltet; geben Sie stattdessen System::Attribute oder Platform::Metadata als Basisklasse an.

[[Attribut](../../windows/attribute.md)] ist nicht mehr die bevorzugte Syntax zum Erstellen von benutzerdefinierten Attributen. Weitere Informationen finden Sie unter [User-Defined Attributes](../../windows/user-defined-attributes-cpp-component-extensions.md). Leiten Sie für CLR-Code Attribute aus `System::Attribute` ab. Leiten Sie für Windows-Runtime-Code Attribute aus `Platform::Metadata` ab.

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