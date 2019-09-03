---
title: conform-Pragma
ms.date: 08/29/2019
f1_keywords:
- conform_CPP
- vc-pragma.conform
helpviewer_keywords:
- conform pragma
- forScope conform pragma
- pragmas, conform
ms.assetid: 71b3e174-c53c-4bfc-adf3-af39b1554191
ms.openlocfilehash: 816ff85bb19f549c6ea072073bd89fcd503545f2
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2019
ms.locfileid: "70220498"
---
# <a name="conform-pragma"></a>conform-Pragma

**C++Zugeschnitten**

Gibt das Laufzeitverhalten der [/Zc: forScope](../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md) -Compileroption an.

## <a name="syntax"></a>Syntax

> **#pragma konform (** *Name* [ **, Show** ] [ **,** { **on** | **Off** }] [[ **,** { **Push** | **Pop** }] [ **,** *Identifier* [ **,** { **on** **aus}** ]  |  ] ] **)**

### <a name="parameters"></a>Parameter

*Benennen*\
Gibt den Namen der zu ändernden Compileroption an. Der einzige gültige *Name* ist `forScope`.

**auftritt**\
Optionale Bewirkt, dass die aktuelle Einstellung des *namens* (true oder false) während der Kompilierung mithilfe einer Warnmeldung angezeigt wird. Beispielsweise `#pragma conform(forScope, show)`.

ein, **aus**\
Optionale Wenn Sie *Name* auf **on** festlegen, wird die [/Zc: forScope](../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md) -Compileroption aktiviert. Der Standardwert ist **Off**.

**Push**\
Optionale Überträgt den aktuellen Wert des *namens* auf den internen compilerstapel. Wenn Sie den *Bezeichner*angeben, können Sie den Wert **on** oder off für *Name* angeben, der auf dem Stapel **abgelegt** werden soll. Beispielsweise `#pragma conform(forScope, push, myname, on)`.

**Chor**\
Optionale Legt den Wert von *Name* auf den Wert oben im internen compilerstapel und dann auf den Stapel. Wenn der Bezeichner mit **Pop**angegeben wird, wird der Stapel zurückgesetzt, bis der Datensatz mit dem *Bezeichner*gefunden wird, der ebenfalls per Pop ausgeblendet wird. der aktuelle Wert für *Name* im nächsten Datensatz auf dem Stapel wird zum neuen Wert für *Name*. Wenn Sie **Pop** mit einem Bezeichner angeben, der sich nicht in einem Datensatz auf dem Stapel befindet, wird der **Pop** ignoriert.

*Figur*\
Optionale Kann in einem **Push** -oder **Pop** -Befehl enthalten sein. Wenn der Bezeichner verwendet wird, kann auch ein **on** -oder **Off** -Spezifizierer verwendet werden.

## <a name="example"></a>Beispiel

```cpp
// pragma_directive_conform.cpp
// compile with: /W1
// C4811 expected
#pragma conform(forScope, show)
#pragma conform(forScope, push, x, on)
#pragma conform(forScope, push, x1, off)
#pragma conform(forScope, push, x2, off)
#pragma conform(forScope, push, x3, off)
#pragma conform(forScope, show)
#pragma conform(forScope, pop, x1)
#pragma conform(forScope, show)

int main() {}
```

## <a name="see-also"></a>Siehe auch

[Pragma-Direktiven und das __Pragma-Schlüsselwort](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
