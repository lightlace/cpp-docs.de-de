---
title: Objekteigene Ressourcen (RAII) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: f86b484e-5a27-4c3b-a92a-dfaa5dd6d93a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 724944028c7343d6b85cf61bde810afcbf1c9619
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46136009"
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

[Willkommen zurück bei C++](../cpp/welcome-back-to-cpp-modern-cpp.md)<br/>
[C++-Programmiersprachenreferenz](../cpp/cpp-language-reference.md)<br/>
[C++-Standardbibliothek](../standard-library/cpp-standard-library-reference.md)