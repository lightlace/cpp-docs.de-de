---
title: inline_recursion-Pragma
ms.date: 08/29/2019
f1_keywords:
- inline_recursion_CPP
- vc-pragma.inline_recursion
helpviewer_keywords:
- pragmas, inline_recursion
- inline_recursion pragma
ms.assetid: cfef5791-63b7-45ac-9574-623747b9b9c9
ms.openlocfilehash: 0169e06e8e47f7b0a7b3f73e809ddc988bcf1e95
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2019
ms.locfileid: "70220952"
---
# <a name="inline_recursion-pragma"></a>inline_recursion-Pragma

Steuert die Inlineerweiterung von direkten oder wechselseitig rekursiven Funktionsaufrufen.

## <a name="syntax"></a>Syntax

> **#Pragma inline_recursion (** [{ **on** | **Off** }] **)**

## <a name="remarks"></a>Hinweise

Verwenden Sie dieses Pragma, um Funktionen zu steuern, die als [Inline](../cpp/inline-functions-cpp.md) -und [__inline](../cpp/inline-functions-cpp.md) -Funktionen oder Funktionen `/Ob2` gekennzeichnet sind, die der Compiler automatisch unter der Option erweitert Die Verwendung dieses Pragmas erfordert die [/ob](../build/reference/ob-inline-function-expansion.md) -compileroptionseinstellung entweder 1 oder 2. Der Standardstatus für **inline_recursion** ist off. Dieses Pragma tritt beim ersten Funktions aufzurufen, nachdem das Pragma angezeigt wird, und wirkt sich nicht auf die Definition der Funktion aus.

Das **inline_recursion** -Pragma steuert, wie rekursive Funktionen erweitert werden. Wenn **inline_recursion** auf Off und eine Inline Funktion sich selbst direkt oder indirekt aufruft, wird die Funktion nur einmal erweitert. Wenn **inline_recursion** auf ON festgelegt ist, wird die Funktion mehrmals erweitert, bis der mit dem [inline_depth](../preprocessor/inline-depth.md) -Pragma festgelegte Wert, der Standardwert für rekursive Funktionen, `inline_depth` der durch das Pragma definiert ist, oder ein Kapazitäts Limit erreicht wird.

## <a name="see-also"></a>Siehe auch

[Pragma-Direktiven und das __Pragma-Schlüsselwort](../preprocessor/pragma-directives-and-the-pragma-keyword.md)\
[inline_depth](../preprocessor/inline-depth.md)\
[/Ob (Inlinefunktionserweiterung)](../build/reference/ob-inline-function-expansion.md)
