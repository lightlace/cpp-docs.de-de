---
title: Objekteigene Ressourcen (RAII)
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: f86b484e-5a27-4c3b-a92a-dfaa5dd6d93a
ms.openlocfilehash: 5705fc1996343141b13e37d1267b2e8c981c1eba
ms.sourcegitcommit: a1fad0a266b20b313364a74b16c9ac45d089b1e9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/11/2019
ms.locfileid: "54220425"
---
# <a name="objects-own-resources-raii"></a>Objekteigene Ressourcen (RAII)

Stellen Sie sicher, dass die eigene Ressourcen Objekte. Dieses Prinzip ist auch bekannt als "Resource Acquisition is Initialization" oder "RAII."

## <a name="example"></a>Beispiel

Übergeben Sie jedes "Neues"-Objekt als Konstruktorargument an einem anderen benannten Objekt, das es (fast immer "unique_ptr") besitzt.

```cpp
void f() {
    unique_ptr<widget> p( new widget() );
    my_class x( new widget() );
    // ...
} // automatic destruction and deallocation for both widget objects
  // automatic exception safety, as if "finally { p->dispose(); x.w.dispose(); }"
```

Übergeben Sie eine neue Ressource immer sofort in ein anderes Objekt, das es besitzt.

```cpp
void g() {
    other_class y( OpenFile() );
    // ...
} // automatic closing and release for file resource
  // automatic exception safety, as if "finally { y.file.dispose(); }"
```

## <a name="see-also"></a>Siehe auch

[Willkommen zurück bei C++ (Modern C++)](../cpp/welcome-back-to-cpp-modern-cpp.md)<br/>
[C++-Programmiersprachenreferenz](../cpp/cpp-language-reference.md)<br/>
[C++-Standardbibliothek](../standard-library/cpp-standard-library-reference.md)
