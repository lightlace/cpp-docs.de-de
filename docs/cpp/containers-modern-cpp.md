---
title: Container (Modern C++)
ms.date: 01/18/2018
ms.topic: conceptual
ms.openlocfilehash: 37b540132fc9ddc03d5eaafd33c545b5db5e7935
ms.sourcegitcommit: effb516760c0f956c6308eeded48851accc96b92
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70926258"
---
# <a name="containers-modern-c"></a>Container (Modern C++)

Verwenden Sie in der Standardeinstellung [Vector](../standard-library/vector-class.md) als bevorzugten sequenziellen C++Container in. Dies entspricht `List<T>` in .NET-Sprachen.

```cpp
vector<string> apples;
apples.push_back("Granny Smith");
```

Verwenden Sie [map](../standard-library/map-class.md) ( `unordered_map`not) als standardmäßigen assoziativen Container. Verwenden Sie [Set](../standard-library/set-class.md), [multimap](../standard-library/multimap-class.md)und [Multiset](../standard-library/multiset-class.md) für degenerierte & mehrere Fälle.

```cpp
map<string, string> apple_color;
// ...
apple_color["Granny Smith"] = "Green";
```

Wenn eine Leistungsoptimierung erforderlich ist, erwägen Sie folgende Verwendungen:

- Der [Arraytyp beim](../standard-library/array-class-stl.md) einbetten ist wichtig, z. b. als Klassenmember.

- Ungeordnete assoziative Container, z. b. [unordered_map](../standard-library/unordered-map-class.md). Diese verfügen über einen niedrigeren pro-Element-Aufwand und eine Konstante Zeit Suche, Sie können jedoch schwieriger und effizient verwendet werden.

- Sortiert `vector`. Weitere Informationen finden Sie unter [Algorithmen](../cpp/algorithms-modern-cpp.md).

Verwenden Sie keine Arrays im C-Stil. Für ältere APIs, die direkten Zugriff auf die Daten benötigen, verwenden Sie `f(vec.data(), vec.size());` stattdessen Accessormethoden wie z. b.

Weitere Informationen zu Containern finden [ C++ Sie unter Standard Bibliothek Container](../standard-library/stl-containers.md).

## <a name="see-also"></a>Siehe auch

[Willkommen zurück bei C++ (Modern C++)](../cpp/welcome-back-to-cpp-modern-cpp.md)<br/>
[C++-Programmiersprachenreferenz](../cpp/cpp-language-reference.md)<br/>
[C++-Standardbibliothek](../standard-library/cpp-standard-library-reference.md)
