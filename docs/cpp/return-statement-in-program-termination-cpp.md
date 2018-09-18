---
title: return-Anweisung in Programmbeendigung (C++) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- data types [C++], function return types
- function return types [C++], return statement
- return keyword [C++], syntax
ms.assetid: 66d002ab-5625-4b68-8446-71e1b8fcdbd8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: cfcf65258767178c0f74f63ca6e938e1d940e3be
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46061135"
---
# <a name="return-statement-in-program-termination-c"></a>return-Anweisung in Programmbeendigung (C++)

Ausgeben einer **zurückgeben** -Anweisung vom `main` ist funktionell gleichwertig mit Aufrufen der `exit` Funktion. Betrachten Sie das folgende Beispiel:

```cpp
// return_statement.cpp
#include <stdlib.h>
int main()
{
    exit( 3 );
    return 3;
}
```

Die `exit` und **zurückgeben** Anweisungen im vorherigen Beispiel funktional identisch sind. Allerdings erfordert C++, dass Funktionen, die andere als Rückgabetypen **"void"** geben einen Wert zurück. Die **zurückgeben** -Anweisung können Sie zum Zurückgeben eines Werts aus `main`.

## <a name="see-also"></a>Siehe auch

[Programmbeendigung](../cpp/program-termination.md)