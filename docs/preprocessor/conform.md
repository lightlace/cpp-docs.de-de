---
title: entsprechen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- conform_CPP
- vc-pragma.conform
dev_langs:
- C++
helpviewer_keywords:
- conform pragma
- forScope conform pragma
- pragmas, conform
ms.assetid: 71b3e174-c53c-4bfc-adf3-af39b1554191
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 05b1f9fef458b8c21de9eb3942730ff901d3922e
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50071231"
---
# <a name="conform"></a>conform
**C++-spezifisch**

Gibt das Verhalten zur Laufzeit die [/Zc: forScope](../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md) -Compileroption.

## <a name="syntax"></a>Syntax

> **#pragma entsprechen (** *Namen* [**, zeigen** ] [**,** { **auf** | **aus** }] [[**,** { **Push** | **pop** }] [**,** *Bezeichner* ]] **)**

### <a name="parameters"></a>Parameter

*name*<br/>
Gibt den Namen der zu ändernden Compileroption an. Der einzige gültige *Namen* ist `forScope`.

**Anzeigen**<br/>
(Optional) Bewirkt, dass die aktuelle Einstellung der *Namen* ("true" oder "false"), die während der Kompilierung mittels einer Warnmeldung angezeigt werden. Beispielsweise `#pragma conform(forScope, show)`.

**auf**, **deaktivieren**<br/>
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