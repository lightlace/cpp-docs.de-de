---
title: Compilerfehler C3099
ms.date: 11/04/2016
f1_keywords:
- C3099
helpviewer_keywords:
- C3099
ms.assetid: b3dded0f-76c9-42c1-991b-532eb8619661
ms.openlocfilehash: 81f508c47c678d86f8f95303861b42f8a70daa57
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74750051"
---
# <a name="compiler-error-c3099"></a>Compilerfehler C3099

'Schlüsselwort': Verwendung des [System::AttributeUsageAttribute] für verwaltete Attribute; Verwendung des [Windows::Foundation::Metadata::AttributeUsageAttribute] für WinRT-Attribute

Verwenden Sie <xref:System.AttributeUsageAttribute>, um **/CLR** -Attribute zu deklarieren. Verwendung von `Windows::Foundation::Metadata::AttributeUsageAttribute` zum Deklarieren von Windows-Runtime-Attributen.

Weitere Informationen zu/CLR-Attributen finden Sie unter [benutzerdefinierte Attribute](../../extensions/user-defined-attributes-cpp-component-extensions.md). Informationen zu unterstützten Attributen in Windows-Runtime finden Sie unter [Windows. Foundation. Metadata-Namespace.](/uwp/api/windows.foundation.metadata)

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C3099 generiert und gezeigt, wie Sie diesen Fehler beheben:

```cpp
// C3099.cpp
// compile with: /clr /c
using namespace System;
[usage(10)]   // C3099
// try the following line instead
// [AttributeUsageAttribute(AttributeTargets::All)]
ref class A : Attribute {};
```
