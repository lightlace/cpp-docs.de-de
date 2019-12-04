---
title: Compilerfehler C2920
ms.date: 11/04/2016
f1_keywords:
- C2920
helpviewer_keywords:
- C2920
ms.assetid: 0a4cb2de-00a0-4209-8160-c7ce6ed7d9ab
ms.openlocfilehash: 2b744729097f7e697c7a7695a849b5ee46d7a4ab
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74761031"
---
# <a name="compiler-error-c2920"></a>Compilerfehler C2920

Neudefinition: 'class': Klassenvorlage oder Generika wurde bereits als 'type' deklariert

Eine generische oder Vorlagenklasse weist mehrere Deklarationen auf, die nicht identisch sind. Verwenden Sie zum Beheben dieses Fehlers unterschiedliche Name für unterschiedlichen Typen, oder entfernen Sie die Neudefinition des Typnamens.

Im folgenden Beispiel wird C2920 generiert und gezeigt, wie Sie diesen Fehler beheben:

```cpp
// C2920.cpp
// compile with: /c
typedef int TC1;
template <class T>
struct TC1 {};   // C2920
struct TC2 {};   // OK - fix by using a different name
```

C2920 kann auch auftreten, wenn Generics verwendet werden:

```cpp
// C2920b.cpp
// compile with: /clr /c
typedef int GC1;
generic <class T>
ref struct GC1 {};   // C2920
ref struct GC2 {};   // OK - fix by using a different name
```
