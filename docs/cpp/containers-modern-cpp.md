---
title: Container (Modern C++)
ms.date: 1/18/2018
ms.topic: conceptual
ms.openlocfilehash: 2da57bfca8b04f50a223dddfb886835c69f746a4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62392335"
---
# <a name="containers-modern-c"></a>Container (Modern C++)

Standardmäßig verwenden [Vektor](../standard-library/vector-class.md) als bevorzugte sequenziellen Container in C++. Dies entspricht dem `List<T>` in .NET-Sprachen.

```cpp
vector<string> apples;
apples.push_back("Granny Smith");
```

Verwendung [Zuordnung](../standard-library/map-class.md) (nicht `unordered_map`) als standardmäßigen assoziativen Container. Verwendung [festgelegt](../standard-library/set-class.md), [mehrfachzuordnung](../standard-library/multimap-class.md), und [Multimenge](../standard-library/multiset-class.md) für degenerierte & mehrfachfälle.

```cpp
map<string, string> apple_color;
// ...
apple_color["Granny Smith"] = "Green";
```

Wenn eine Leistungsoptimierung erforderlich ist, erwägen Sie folgende Verwendungen:

- Die [Array](../standard-library/array-class-stl.md) eingeben, wenn das Einbetten wichtig ist, z. B. ein Klassenmember ist.

- Ungeordnete assoziative Container wie z. B. ["unordered_map"](../standard-library/unordered-map-class.md). Diese weisen Mehraufwand pro Element niedriger und Konstante zeitsuche, aber sie können schwieriger, korrekt und effizient zu verwenden.

- Sortiert `vector`. Weitere Informationen finden Sie unter [Algorithmen](../cpp/algorithms-modern-cpp.md).

Verwenden Sie keine Arrays im C-Stil. Für ältere APIs, die Zugriff auf die Daten weiterleiten müssen Accessormethoden verwenden, z. B. `f(vec.data(), vec.size());` stattdessen.

Weitere Informationen zu Containern finden Sie unter [C++-Standardbibliothekcontainer](../standard-library/stl-containers.md).

## <a name="see-also"></a>Siehe auch

[Willkommen zurück bei C++ (Modern C++)](../cpp/welcome-back-to-cpp-modern-cpp.md)<br/>
[C++-Programmiersprachenreferenz](../cpp/cpp-language-reference.md)<br/>
[C++-Standardbibliothek](../standard-library/cpp-standard-library-reference.md)
