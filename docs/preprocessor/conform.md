---
title: conform
ms.date: 11/04/2016
f1_keywords:
- conform_CPP
- vc-pragma.conform
helpviewer_keywords:
- conform pragma
- forScope conform pragma
- pragmas, conform
ms.assetid: 71b3e174-c53c-4bfc-adf3-af39b1554191
ms.openlocfilehash: 35c3b06106779a9056f682ff76c6ed4b4ab1ab41
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/05/2019
ms.locfileid: "59026577"
---
# <a name="conform"></a>conform
**C++-spezifisch**

Gibt das Verhalten zur Laufzeit die [/Zc: forScope](../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md) -Compileroption.

## <a name="syntax"></a>Syntax

> **#pragma entsprechen (** *Namen* [**, zeigen** ] [**,** { **auf** | **aus** }] [[**,** { **Push** | **pop** }] [**,** *Bezeichner* ]] **)**

### <a name="parameters"></a>Parameter

*Name*<br/>
Gibt den Namen der zu ändernden Compileroption an. Der einzige gültige *Namen* ist `forScope`.

**show**<br/>
(Optional) Bewirkt, dass die aktuelle Einstellung der *Namen* ("true" oder "false"), die während der Kompilierung mittels einer Warnmeldung angezeigt werden. Beispielsweise `#pragma conform(forScope, show)`.

**on**, **off**<br/>
(Optional) Festlegen von *Namen* zu **auf** ermöglicht die [/Zc: forScope](../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md) -Compileroption. Der Standardwert ist **aus**.

**push**<br/>
(Optional) Legt den aktuellen Wert der *Namen* auf dem internen compilerstapel ab. Bei Angabe von *Bezeichner*, können Sie angeben, die **auf** oder **aus** Wert für *Namen* auf den Stapel verschoben werden. Beispielsweise `#pragma conform(forScope, push, myname, on)`.

**pop**<br/>
(Optional) Legt den Wert der *Namen* auf den Wert am Anfang der internen Compilerstapels fest und ruft dann den Stapel. Wenn Bezeichner angegeben wird **pop**, die Stapel zurück, bis er feststellt, dass den Datensatz mit *Bezeichner*, die ebenfalls entfernt wird; der aktuelle Wert für *Namen* in der nächste Datensatz im Stapel wird der neue Wert für *Namen*. Bei Angabe von **pop** mit einer *Bezeichner* das ist nicht in einem Datensatz auf dem Stapel, der **pop** wird ignoriert.

*identifier*<br/>
(Optional) Können mit einbezogen werden eine **Push** oder **pop** Befehl. Wenn *Bezeichner* verwendet wird, wird eine **auf** oder **aus** Bezeichner kann auch verwendet werden.

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