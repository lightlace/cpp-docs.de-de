---
title: return-Anweisung in Programmbeendigung (C++)
ms.date: 11/04/2016
helpviewer_keywords:
- data types [C++], function return types
- function return types [C++], return statement
- return keyword [C++], syntax
ms.assetid: 66d002ab-5625-4b68-8446-71e1b8fcdbd8
ms.openlocfilehash: 9c7b6130ee1a0b49ab75a70d84764d3a1f8c5ef0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62267611"
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