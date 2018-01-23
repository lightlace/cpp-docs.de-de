---
title: Container (Modern C++) | Microsoft Docs
ms.custom: 
ms.date: 1/18/2018
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d43570f644e9627de5a40fc5b824a17e4fd33ffc
ms.sourcegitcommit: 6f40bba1772a09ff0e3843d5f70b553e1a15ab50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2018
---
# <a name="containers-modern-c"></a>Container (Modern C++)

Standardmäßig verwenden [Vektor](../standard-library/vector-class.md) als der bevorzugte sequenziellen Container in C++. Dies entspricht dem `List<T>` in .NET-Sprachen.

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

- Die [Array](../standard-library/array-class-stl.md) eingeben, wenn das Einbetten wichtig ist, z. B. einen Klassenmember ist.

- Ungeordnete assoziative Container wie z. B. ["unordered_map"](../standard-library/unordered-map-class.md). Diese weisen Mehraufwand pro Element niedriger und Konstante zeitsuche, aber sie können schwieriger zu ordnungsgemäß und effizient zu verwenden.

- Sortiert **Vektor**. Weitere Informationen finden Sie unter [Algorithmen](../cpp/algorithms-modern-cpp.md).

Verwenden Sie keine Arrays im C-Stil. Verwenden Sie für ältere APIs, die Zugriff auf die Daten weiterleiten müssen, z. B. Methoden des Eigenschaftenaccessors `f(vec.data(), vec.size());` stattdessen.

Weitere Informationen zu Containern finden Sie unter [Standard C++-Bibliothek-Container](../standard-library/stl-containers.md).

## <a name="see-also"></a>Siehe auch

[Willkommen zurück bei C++](../cpp/welcome-back-to-cpp-modern-cpp.md)  
[C++-Programmiersprachenreferenz](../cpp/cpp-language-reference.md)  
[C++-Standardbibliothek](../standard-library/cpp-standard-library-reference.md)  
