---
title: Arrays in Ausdrücken | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- expressions [C++], arrays in
- arrays [C++], in expressions
ms.assetid: 6e5a795b-d6bd-4e39-b313-6a20d47c4d4b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 34f8a45dfa9de9a5a48e13cb6a38f667e5963f2d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46068545"
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