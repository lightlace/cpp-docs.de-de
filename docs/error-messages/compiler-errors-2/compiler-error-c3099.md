---
title: Compilerfehler C3099
ms.date: 11/04/2016
f1_keywords:
- C3099
helpviewer_keywords:
- C3099
ms.assetid: b3dded0f-76c9-42c1-991b-532eb8619661
ms.openlocfilehash: 0f3eac1c232ef159d220a347d6b6dc3aed2fdd9a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62324778"
---
# <a name="compiler-error-c3099"></a>Compilerfehler C3099

'Schlüsselwort': Verwendung des [System::AttributeUsageAttribute] für verwaltete Attribute; Verwendung des [Windows::Foundation::Metadata::AttributeUsageAttribute] für WinRT-Attribute

Verwendung <xref:System.AttributeUsageAttribute> deklarieren **"/ CLR"** Attribute. Verwendung von `Windows::Foundation::Metadata::AttributeUsageAttribute` zum Deklarieren von Windows-Runtime-Attributen.

Weitere Informationen zu CLR-Attributen finden Sie unter [User-Defined Attributes](../../extensions/user-defined-attributes-cpp-component-extensions.md). Unterstützte Attribute in Windows-Runtime, finden Sie unter [Windows.Foundation.Metadata-Namespace](/uwp/api/windows.foundation.metadata)

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C3099 generiert und gezeigt, wie Sie diesen Fehler beheben:

```
// C3099.cpp
// compile with: /clr /c
using namespace System;
[usage(10)]   // C3099
// try the following line instead
// [AttributeUsageAttribute(AttributeTargets::All)]
ref class A : Attribute {};
```