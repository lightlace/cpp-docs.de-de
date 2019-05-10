---
title: Compilerfehler C2653
ms.date: 11/30/2017
f1_keywords:
- C2653
helpviewer_keywords:
- C2653
ms.assetid: 3f49e731-affd-43a0-a8d0-181db7650bc3
ms.openlocfilehash: 2882764e1c0a84634c500d920f327fbebc4b19a9
ms.sourcegitcommit: 7d64c5f226f925642a25e07498567df8bebb00d4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2019
ms.locfileid: "65447940"
---
# <a name="compiler-error-c2653"></a>Compilerfehler C2653

> "*Bezeichner*": ist kein Name für eine Klasse oder Namespace

Die Sprachsyntax ist erforderlich, eine Klasse, Struktur, Union oder hier die Namespacenamen ein.

Dieser Fehler kann auftreten, wenn Sie einen Namen verwenden, der nicht als eine Klasse, Struktur, Union oder vor einen Bereichsoperator-Namespace deklariert wurde. Um dieses Problem zu beheben, deklarieren Sie den Namen oder den Header, der den Namen deklariert, bevor sie verwendet wird.

C2653 ist auch möglich, wenn Sie versuchen, Sie definieren eine *zusammengesetzten Namespace*, einen Namespace, der einen oder mehrere Bereich geschachtelten Namespacenamen enthält. Zusammengesetzte Namespace Definitionen in C++ vor C ++ 17 sind nicht zulässig. Zusammengesetzte Namespaces werden unterstützt, starten in Visual Studio 2015 Update 3, bei der Angabe der [/Std: c ++ neueste](../../build/reference/std-specify-language-standard-version.md) -Compileroption. Ab Visual Studio 2017 Version 15.5 ist der Compiler unterstützt die zusammengesetzte Namespacedefinitionen bei der [/Std: c ++ 17](../../build/reference/std-specify-language-standard-version.md) angegeben wird.

## <a name="examples"></a>Beispiele

In diesem Beispiel wird C2653 generiert, da ein Bereichsname verwendet wird, aber nicht deklariert. Der Compiler erwartet, dass eine Klasse, Struktur, Union oder Namespacenamen, bevor Sie einen Bereichsoperator (:).

```cpp
// C2653.cpp
// compile with: /c
class yy {
   void func1(int i);
};

void xx::func1(int m) {}   // C2653, xx is not declared
void yy::func1(int m) {}   // OK
```

Im Code, der nicht für C ++ 17 oder höher Standards kompiliert wird, müssen die geschachtelten Namespaces eine explizite Namespacedeklaration auf jeder Schachtelungsebene verwenden:

```cpp
// C2653b.cpp
namespace a::b {int i;}   // C2653 prior to Visual Studio 2015 Update 3,
                          // C2429 thereafter. Use /std:c++17 or /std:c++latest to fix.

namespace a {             // Use this form for compliant code under /std:c++14 (the default)
   namespace b {          // or when using compilers before Visual Studio 2015 update 3.
      int i;
   }
}

int main() {
   a::b::i = 2;
}
```
