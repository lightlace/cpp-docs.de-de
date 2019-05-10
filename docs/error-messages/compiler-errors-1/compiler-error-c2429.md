---
title: Compilerfehler C2429
ms.date: 11/16/2017
f1_keywords:
- C2429
helpviewer_keywords:
- C2429
ms.assetid: 57ff6df9-5cf1-49f3-8bd8-4e550dfd65a0
ms.openlocfilehash: a5d1e98e91c541729a93f731eede9b047589c63a
ms.sourcegitcommit: 7d64c5f226f925642a25e07498567df8bebb00d4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2019
ms.locfileid: "65447984"
---
# <a name="compiler-error-c2429"></a>Compilerfehler C2429

> "*Sprachfunktion*"erfordert die compilerkennzeichnung"*Compileroption*"

Die Sprachfunktion erfordert eine bestimmte Compileroption für die Unterstützung.

Der Fehler **C2429: Sprachfeature "nested-Namespace-Definition" erfordert die compilerkennzeichnung "/ Std: c ++ 17"** wird generiert, wenn Sie versuchen, Sie definieren eine *zusammengesetzten Namespace*, einen Namespace, eine oder mehrere enthält, Bereich geschachtelten Namespacenamen, Visual Studio 2015 Update 5 ab. (In Visual Studio 2017 Version 15.3 führt das **/Std: c ++ neueste** Schalter ist erforderlich.) Zusammengesetzte Namespace Definitionen in C++ vor C ++ 17 sind nicht zulässig. Der Compiler unterstützt die zusammengesetzte Namespacedefinitionen bei der [/Std: c ++ 17](../../build/reference/std-specify-language-standard-version.md) -Compileroption angegeben wird:

```cpp
// C2429a.cpp
namespace a::b { int i; } // C2429 starting in Visual Studio 2015 Update 3.
                          // Use /std:c++17 to fix, or do this:
// namespace a { namespace b { int i; }}

int main() {
   a::b::i = 2;
}
```
