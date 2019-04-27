---
title: Compilerfehler C2872
ms.date: 11/04/2016
f1_keywords:
- C2872
helpviewer_keywords:
- C2872
ms.assetid: c619ef97-6e0e-41d7-867c-f8d28a07d553
ms.openlocfilehash: 103998c7872b683c7405796ee28bd550246ae9bf
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62257609"
---
# <a name="compiler-error-c2872"></a>Compilerfehler C2872

"*Symbol*': Mehrdeutiges Symbol

Der Compiler ermitteln nicht, welches Symbol auf verwiesen wird. Mehr als ein Symbol mit dem angegebenen Namen, liegt im Bereich. Finden Sie unter den Hinweisen im Anschluss an der Fehlermeldung für die Speicherorte und die Deklarationen der Compiler für die Mehrdeutiges Symbol gefunden. Um dieses Problem zu beheben, können Sie vollständig mehrdeutige Symbol qualifizieren, z. B. einen Namespace mit `std::byte` oder `::byte`. Sie können auch eine [Namespacealias](../../cpp/namespaces-cpp.md#namespace_aliases) einem enthaltenen Namespace einen passenden kurze Namen für die Verwendung gewähren, wenn die Symbole in Ihrem Quellcode eindeutig zu machen.

C2872 kann auftreten, wenn eine Headerdatei umfasst eine [using-Direktive](../../cpp/namespaces-cpp.md#using_directives), und eine nachfolgenden Header-Datei enthalten ist, die einen Typ, der auch in den im angegebenen Namespace enthält die `using` Richtlinie. Geben Sie einen `using` Direktive erst alle Headerdateien werden mit angegeben `#include`.

C2872 kann in Visual Studio 2013 auftreten, aufgrund eines Konflikts zwischen der `Windows::Foundation::Metadata::Platform` Enum Typ und den C++ / CX definierte `Platform` Namespace. Um dieses Problem zu umgehen, gehen Sie folgendermaßen vor:

- Entfernen Sie die "using Namespace Windows::Foundation::Metadata"-Klausel aus den Projektdateien.

- Geben Sie den vollqualifizierten Namen für jeden Typ, der in diesem Namespace enthalten ist.

## <a name="example"></a>Beispiel

Das folgende Beispiel generiert C2872, da ein mehrdeutiger Verweis auf eine Variable namens erfolgt `i`; zwei Variablen mit demselben Namen befinden sich im Gültigkeitsbereich:

```cpp
// C2872.cpp
// compile with: cl /EHsc C2872.cpp
namespace A {
   int i;
}

using namespace A;
int i;
int main() {
   ::i++;   // ok, uses i from global namespace
   A::i++;   // ok, uses i from namespace A
   i++;   // C2872 ambiguous: ::i or A::i?
   // To fix this issue, use the fully qualified name
   // for the intended variable.
}
```
