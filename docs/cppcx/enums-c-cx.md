---
title: Enumerationen (C++/CX)
ms.date: 12/30/2016
ms.assetid: 99fbbe28-c1cd-43af-9ead-60f90eba6e68
ms.openlocfilehash: be11d8d8f38a92fbe4be00eed53dd5226bab0b59
ms.sourcegitcommit: b8c22e6d555cf833510753cba7a368d57e5886db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76821752"
---
# <a name="enums-ccx"></a>Enumerationen (C++/CX)

C++/CX unterstützt das `public enum class`-Schlüsselwort, das Analog zu C++ einem Standard `scoped  enum`ist. Wenn Sie einen Enumerator verwenden, der durch das Schlüsselwort `public enum class` deklariert ist, müssen Sie den Enumerationsbezeichner dazu benutzen, den Umfang jedes Enumeratorwerts festzulegen.

### <a name="remarks"></a>Hinweise

Eine `public enum class` , die keinen Zugriffsspezifizierer hat, z. B. `public`, wird als standardmäßige [Enumeration mit C++-Bereichseinschränkung](../cpp/enumerations-cpp.md)behandelt.

Eine `public enum class`-oder `public enum struct` Deklaration kann einen zugrunde liegenden Typ eines beliebigen ganzzahligen Typs aufweisen, obwohl der Windows-Runtime selbst erfordert, dass der Typ "Int32" oder "UInt32" für eine Flags-Enum ist. Die folgende Syntax beschreibt die Teile einer `public enum class` oder `public enum struct`.

Dieses Beispiel zeigt, wie eine öffentliche Enumerationsklasse definiert wird:

[!code-cpp[cx_enums#01](../cppcx/codesnippet/CPP/cpp/class1.h#01)]

In diesem folgenden Beispiel wird zeigt, wie sie verwendet wird:

[!code-cpp[cx_enums#02](../cppcx/codesnippet/CPP/cpp/class1.h#02)]

### <a name="examples"></a>Beispiele

In den folgenden Beispielen wird veranschaulicht, wie eine Enumeration deklariert wird.

[!code-cpp[cx_enums#03](../cppcx/codesnippet/CPP/cpp/class1.h#03)]

Im nächsten Beispiel wird gezeigt, wie Sie eine Enumeration in numerische Werte umwandeln und Vergleiche durchführen. Beachten Sie, dass die Verwendung des Enumerators `One` vom Enumerationsbezeichner `Enum1` beschränkt wird, und der Enumerator `First` wird durch `Enum2`beschränkt.

[!code-cpp[cx_enums#04](../cppcx/codesnippet/CPP/cpp/class1.h#04)]

## <a name="see-also"></a>Siehe auch

[Typsystem](../cppcx/type-system-c-cx.md)<br/>
[C++-/CX-Programmiersprachenreferenz](../cppcx/visual-c-language-reference-c-cx.md)<br/>
[Referenz zu Namespaces](../cppcx/namespaces-reference-c-cx.md)
