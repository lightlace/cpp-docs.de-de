---
title: Container (Modern C++) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 1/18/2018
ms.technology:
- cpp-language
ms.topic: conceptual
dev_langs:
- C++
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d740bb36c1d574e474058c05d900d605c71e55f0
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/01/2018
ms.locfileid: "39406333"
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
 [Willkommen zurück bei C++](../cpp/welcome-back-to-cpp-modern-cpp.md)  
 [C++-Programmiersprachenreferenz](../cpp/cpp-language-reference.md)  
 [C++-Standardbibliothek](../standard-library/cpp-standard-library-reference.md)  