---
title: Compilerfehler C2720
ms.date: 11/04/2016
f1_keywords:
- C2720
helpviewer_keywords:
- C2720
ms.assetid: 9ee3aab7-711b-4f5a-b2f1-cb62b130f1ce
ms.openlocfilehash: c6499fd3f279099ea7c5b31860e70bdaa285e3f9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62383047"
---
# <a name="compiler-error-c2720"></a>Compilerfehler C2720

> "*Bezeichner*': '*Spezifizierer*" Speicherklassenspezifizierer für Elemente unzulässig

Die Speicherklasse kann für Klassenmember außerhalb der Variablendeklaration verwendet werden. Um diesen Fehler zu beheben, entfernen Sie den nicht benötigten [Speicherklasse](../../cpp/storage-classes-cpp.md) -Bezeichner aus der Definition des Members außerhalb der Klassendeklaration.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C2720 generiert und gezeigt, wie Sie diesen Fehler beheben:

```cpp
// C2720.cpp
struct S {
   static int i;
};
static S::i;   // C2720 - remove the unneeded 'static' to fix it
```