---
title: Compilerfehler C3888
ms.date: 11/04/2016
f1_keywords:
- C3888
helpviewer_keywords:
- C3888
ms.assetid: 40820812-79c5-4dcd-a19d-b4164d25fc8a
ms.openlocfilehash: e4d52946126e7be6c6f2aef34b5eb5a93a0babad
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/05/2019
ms.locfileid: "59033640"
---
# <a name="compiler-error-c3888"></a>Compilerfehler C3888

"name": Der diesem literal-Datenmember zugeordnete Konstantenausdruck wird von C++/CLI nicht unterstützt

Das *name* -Datenmember, das mit dem [literal](../../extensions/literal-cpp-component-extensions.md) -Schlüsselwort deklariert wird, wird mit einem Wert initialisiert, der vom Compiler nicht unterstützt wird. Der Compiler unterstützt nur konstante integrale, Enumerations- oder Zeichenfolgentypen. Der Fehler **C3888** wurde wahrscheinlich dadurch verursacht, dass das Datenmember mit einem Bytearray initialisiert wird.

### <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler

1. Vergewissern Sie sich, dass das deklarierte literal-Datenmember ein unterstützter Typ ist.

## <a name="see-also"></a>Siehe auch

[literal](../../extensions/literal-cpp-component-extensions.md)