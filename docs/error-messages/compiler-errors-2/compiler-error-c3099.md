---
title: Compilerfehler C3099 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3099
dev_langs:
- C++
helpviewer_keywords:
- C3099
ms.assetid: b3dded0f-76c9-42c1-991b-532eb8619661
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c5f11e049965fb7374a2294e813502d1279f9f26
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46067414"
---
# <a name="compiler-error-c3099"></a>Compilerfehler C3099

'Schlüsselwort': Verwendung des [System::AttributeUsageAttribute] für verwaltete Attribute; Verwendung des [Windows::Foundation::Metadata::AttributeUsageAttribute] für WinRT-Attribute

Verwendung <xref:System.AttributeUsageAttribute> deklarieren **"/ CLR"** Attribute. Verwendung von `Windows::Foundation::Metadata::AttributeUsageAttribute` zum Deklarieren von Windows-Runtime-Attributen.

Weitere Informationen zu CLR-Attributen finden Sie unter [User-Defined Attributes](../../windows/user-defined-attributes-cpp-component-extensions.md). Unterstützte Attribute in Windows-Runtime, finden Sie unter [Windows.Foundation.Metadata-Namespace](https://msdn.microsoft.com/library/windows/apps/windows.foundation.metadata.aspx)

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