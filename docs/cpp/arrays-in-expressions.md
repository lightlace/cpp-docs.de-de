---
title: Arrays in Ausdrücken
ms.date: 11/04/2016
helpviewer_keywords:
- expressions [C++], arrays in
- arrays [C++], in expressions
ms.assetid: 6e5a795b-d6bd-4e39-b313-6a20d47c4d4b
ms.openlocfilehash: 0f2ef43c2a5bc4f8a44378c21d6d53b14f07ea07
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62184375"
---
# <a name="arrays-in-expressions"></a>Arrays in Ausdrücken

Wenn ein Bezeichner eines Arraytyps tritt in einem Ausdruck als `sizeof`, Adresse des (**&**), oder Initialisieren eines Verweises, wird er in einen Zeiger auf das erste Arrayelement konvertiert. Zum Beispiel:

```cpp
char szError1[] = "Error: Disk drive not ready.";
char *psz = szError1;
```

Der Zeiger `psz` zeigt auf das erste Element des Arrays `szError1`. Beachten Sie, dass Arrays, im Gegensatz zu Zeigern, nicht veränderbare l-Werte sind. Daher ist die folgende Zuordnung ungültig:

```cpp
szError1 = psz;
```

## <a name="see-also"></a>Siehe auch

[Arrays](../cpp/arrays-cpp.md)