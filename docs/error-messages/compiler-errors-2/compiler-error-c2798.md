---
title: Compilerfehler C2798
ms.date: 11/04/2016
f1_keywords:
- C2798
helpviewer_keywords:
- C2798
ms.assetid: fb0cd861-b228-4f81-8090-e28344a727e0
ms.openlocfilehash: 6eed1f1aad0783f9e1d5f4126847b54f6b7278e0
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74739202"
---
# <a name="compiler-error-c2798"></a>Compilerfehler C2798

"Super:: Member" ist mehrdeutig.

Mehrere geerbte Strukturen enthalten den Member, auf den Sie mit [Super](../../cpp/super.md)verwiesen haben. Sie können den Fehler wie folgt beheben:

- Entfernen von B1 oder B2 aus der Vererbungs Liste von D.

- Ändern des Namens des Datenelements in B1 oder B2.

Im folgenden Beispiel wird C2798 generiert:

```cpp
// C2798.cpp
struct B1 {
   int i;
};

struct B2 {
   int i;
};

struct D : B1, B2 {
   void g() {
      __super::i = 4; // C2798
   }
};
```
