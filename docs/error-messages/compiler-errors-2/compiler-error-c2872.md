---
title: Compilerfehler C2872 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2872
dev_langs:
- C++
helpviewer_keywords:
- C2872
ms.assetid: c619ef97-6e0e-41d7-867c-f8d28a07d553
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 038c3475a6041dfb719bb2270a87ac2898f8b958
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46036756"
---
# <a name="compiler-error-c2872"></a>Compilerfehler C2872

"*Symbol*': Mehrdeutiges Symbol

Der Compiler ermitteln nicht, welches Symbol auf verwiesen wird. Mehr als ein Symbol mit dem angegebenen Namen, liegt im Bereich. Finden Sie unter den Hinweisen im Anschluss an der Fehlermeldung für die Speicherorte und die Deklarationen der Compiler für die Mehrdeutiges Symbol gefunden. Um dieses Problem zu beheben, können Sie vollständig mehrdeutige Symbol qualifizieren, z. B. einen Namespace mit `std::byte` oder `::byte`. Sie können auch eine [Namespacealias](../../cpp/namespaces-cpp.md#namespace_aliases) einem enthaltenen Namespace einen passenden kurze Namen für die Verwendung gewähren, wenn die Symbole in Ihrem Quellcode eindeutig zu machen.

C2872 kann auftreten, wenn eine Headerdatei umfasst eine [using-Direktive](../../cpp/namespaces-cpp.md#using_directives), und eine nachfolgenden Header-Datei enthalten ist, die einen Typ, der auch in den im angegebenen Namespace enthält die `using` Richtlinie. Geben Sie einen `using` Direktive erst alle Headerdateien werden mit angegeben `#include`.

Finden Sie weitere Informationen zu C2872, Knowledge Base-Artikel [PRB: Compiler Fehler bei der Sie verwenden #import mit XML in Visual C++ .NET](http://support.microsoft.com/kb/316317) und ["Fehler C2872: 'Platform': Mehrdeutiges Symbol" Fehlermeldung bei Verwendung der Windows::Foundation::Metadata-Namespace in Visual Studio 2013](https://support.microsoft.com/kb/2890859).

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