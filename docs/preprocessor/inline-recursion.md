---
title: inline_recursion
ms.date: 11/04/2016
f1_keywords:
- inline_recursion_CPP
- vc-pragma.inline_recursion
helpviewer_keywords:
- pragmas, inline_recursion
- inline_recursion pragma
ms.assetid: cfef5791-63b7-45ac-9574-623747b9b9c9
ms.openlocfilehash: 80ffabc6ac7c95fd7d9fb4e62bea38c2a04b04f0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62383697"
---
# <a name="inlinerecursion"></a>inline_recursion
Steuert die Inlineerweiterung von direkten oder wechselseitig rekursiven Funktionsaufrufen.

## <a name="syntax"></a>Syntax

```
#pragma inline_recursion( [{on | off}] )
```

## <a name="remarks"></a>Hinweise

Mit diesem Pragma Steuerungsfunktionen für die als markiert [Inline](../cpp/inline-functions-cpp.md) und ["__inline"](../cpp/inline-functions-cpp.md) oder Funktionen, die der Compiler automatisch unter Erweitert die `/Ob2` Option. Verwendung dieses Pragmas erfordert eine [tatsächlich](../build/reference/ob-inline-function-expansion.md) Einstellung von 1 oder 2. Der Standardzustand für **Inline_recursion** ist deaktiviert. Dieses Pragma tritt mit dem ersten Funktionsaufruf in Kraft, nachdem das Pragma angezeigt wird, und hat keinen Einfluss auf die Definition der Funktion.

Die **Inline_recursion** Pragma steuert, wie rekursive Funktionen erweitert werden. Wenn **Inline_recursion** ist deaktiviert und ist eine Inlinefunktion sich selbst (entweder direkt oder indirekt), die Funktion aufruft, nur einmal erweitert. Wenn **Inline_recursion** ist, wird die Funktion mehrmals erweitert, bis sie den mit festgelegten Wert erreicht die [Inline_depth](../preprocessor/inline-depth.md) Pragma, der Standardwert für rekursive Funktionen, die durch die definiertist`inline_depth` -Pragma, oder eine Kapazität zu beschränken.

## <a name="see-also"></a>Siehe auch

[Pragma-Direktiven und das __Pragma-Schlüsselwort](../preprocessor/pragma-directives-and-the-pragma-keyword.md)<br/>
[inline_depth](../preprocessor/inline-depth.md)<br/>
[/Ob (Inlinefunktionserweiterung)](../build/reference/ob-inline-function-expansion.md)